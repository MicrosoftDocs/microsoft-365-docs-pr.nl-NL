---
title: Entiteiten onderzoeken op apparaten met livereactie in Microsoft Defender voor Eindpunt
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
ms.openlocfilehash: d5e48f1e4f6bc2cfaa836d90e24f2ce8ba3f2114
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845328"
---
# <a name="investigate-entities-on-devices-using-live-response"></a><span data-ttu-id="6a1f8-104">Entiteiten op apparaten onderzoeken met livereactie</span><span class="sxs-lookup"><span data-stu-id="6a1f8-104">Investigate entities on devices using live response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6a1f8-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="6a1f8-105">**Applies to:**</span></span>
- [<span data-ttu-id="6a1f8-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="6a1f8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6a1f8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6a1f8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="6a1f8-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="6a1f8-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="6a1f8-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="6a1f8-110">Live response geeft beveiligingsbewerkingen teams direct toegang tot een apparaat (ook wel een computer genoemd) met behulp van een externe shell-verbinding.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-110">Live response gives security operations teams instantaneous access to a device (also referred to as a machine) using a remote shell connection.</span></span> <span data-ttu-id="6a1f8-111">Dit geeft u de macht om uitgebreid onderzoek te doen en direct actie te ondernemen om snel geïdentificeerde bedreigingen in realtime te bevatten.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-111">This gives you the power to do in-depth investigative work and take immediate response actions to promptly contain identified threats—in real time.</span></span> 

<span data-ttu-id="6a1f8-112">Live response is ontworpen om onderzoeken te verbeteren door uw beveiligingsteam in staat te stellen om gerechtelijke gegevens te verzamelen, scripts uit te voeren, verdachte entiteiten te verzenden voor analyse, bedreigingen te corrigeren en proactief te zoeken naar nieuwe bedreigingen.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-112">Live response is designed to enhance investigations by enabling your security operations team to collect forensic data, run scripts, send suspicious entities for analysis, remediate threats, and proactively hunt for emerging threats.</span></span><br/><br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4qLUW]

<span data-ttu-id="6a1f8-113">Met livereactie kunnen analisten alle volgende taken uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="6a1f8-113">With live response, analysts can do all of the following tasks:</span></span>
- <span data-ttu-id="6a1f8-114">Voer eenvoudige en geavanceerde opdrachten uit om onderzoek te doen op een apparaat.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-114">Run basic and advanced commands to do investigative work on a device.</span></span>
- <span data-ttu-id="6a1f8-115">Download bestanden zoals malwarevoorbeelden en resultaten van PowerShell-scripts.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-115">Download files such as malware samples and outcomes of PowerShell scripts.</span></span>
- <span data-ttu-id="6a1f8-116">Bestanden op de achtergrond downloaden (nieuw!).</span><span class="sxs-lookup"><span data-stu-id="6a1f8-116">Download files in the background (new!).</span></span>
- <span data-ttu-id="6a1f8-117">Upload PowerShell-script of uitvoerbaar voor de bibliotheek en voer het uit op een apparaat op tenantniveau.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-117">Upload a PowerShell script or executable to the library and run it on a device from a tenant level.</span></span>
- <span data-ttu-id="6a1f8-118">Herstelacties uitvoeren of ongedaan maken.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-118">Take or undo remediation actions.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="6a1f8-119">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="6a1f8-119">Before you begin</span></span>

<span data-ttu-id="6a1f8-120">Voordat u een sessie op een apparaat kunt starten, moet u aan de volgende vereisten voldoen:</span><span class="sxs-lookup"><span data-stu-id="6a1f8-120">Before you can initiate a session on a device, make sure you fulfill the following requirements:</span></span>

- <span data-ttu-id="6a1f8-121">**Controleer of u een ondersteunde versie** van Windows.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-121">**Verify that you're running a supported version of Windows**.</span></span> <br/>
<span data-ttu-id="6a1f8-122">Apparaten moeten een van de volgende versies van Windows</span><span class="sxs-lookup"><span data-stu-id="6a1f8-122">Devices must be running one of the following versions of Windows</span></span>

  - <span data-ttu-id="6a1f8-123">**Windows 10**</span><span class="sxs-lookup"><span data-stu-id="6a1f8-123">**Windows 10**</span></span>
    - <span data-ttu-id="6a1f8-124">[Versie 1909](/windows/whats-new/whats-new-windows-10-version-1909) of hoger</span><span class="sxs-lookup"><span data-stu-id="6a1f8-124">[Version 1909](/windows/whats-new/whats-new-windows-10-version-1909) or later</span></span>  
    - <span data-ttu-id="6a1f8-125">[Versie 1903](/windows/whats-new/whats-new-windows-10-version-1903) met [KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)</span><span class="sxs-lookup"><span data-stu-id="6a1f8-125">[Version 1903](/windows/whats-new/whats-new-windows-10-version-1903) with [KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)</span></span>
    - <span data-ttu-id="6a1f8-126">[Versie 1809 (RS 5)](/windows/whats-new/whats-new-windows-10-version-1809) [met KB4537818](https://support.microsoft.com/help/4537818/windows-10-update-kb4537818)</span><span class="sxs-lookup"><span data-stu-id="6a1f8-126">[Version 1809 (RS 5)](/windows/whats-new/whats-new-windows-10-version-1809) with [with KB4537818](https://support.microsoft.com/help/4537818/windows-10-update-kb4537818)</span></span>
    - <span data-ttu-id="6a1f8-127">[Versie 1803 (RS 4)](/windows/whats-new/whats-new-windows-10-version-1803) met [KB4537795](https://support.microsoft.com/help/4537795/windows-10-update-kb4537795)</span><span class="sxs-lookup"><span data-stu-id="6a1f8-127">[Version 1803 (RS 4)](/windows/whats-new/whats-new-windows-10-version-1803) with [KB4537795](https://support.microsoft.com/help/4537795/windows-10-update-kb4537795)</span></span>
    - <span data-ttu-id="6a1f8-128">[Versie 1709 (RS 3)](/windows/whats-new/whats-new-windows-10-version-1709) met [KB4537816](https://support.microsoft.com/help/4537816/windows-10-update-kb4537816)</span><span class="sxs-lookup"><span data-stu-id="6a1f8-128">[Version 1709 (RS 3)](/windows/whats-new/whats-new-windows-10-version-1709) with [KB4537816](https://support.microsoft.com/help/4537816/windows-10-update-kb4537816)</span></span>
  
  - <span data-ttu-id="6a1f8-129">**Windows Server 2019 - Alleen van toepassing op openbare preview**</span><span class="sxs-lookup"><span data-stu-id="6a1f8-129">**Windows Server 2019 - Only applicable for Public preview**</span></span>
    - <span data-ttu-id="6a1f8-130">Versie 1903 of (met [KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)) later</span><span class="sxs-lookup"><span data-stu-id="6a1f8-130">Version 1903 or (with [KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)) later</span></span> 
    - <span data-ttu-id="6a1f8-131">Versie 1809 (met [KB4537818](https://support.microsoft.com/en-us/help/4537818/windows-10-update-kb4537818))</span><span class="sxs-lookup"><span data-stu-id="6a1f8-131">Version 1809 (with [KB4537818](https://support.microsoft.com/en-us/help/4537818/windows-10-update-kb4537818))</span></span>

- <span data-ttu-id="6a1f8-132">**Schakel livereactie in vanaf de pagina met geavanceerde instellingen.**</span><span class="sxs-lookup"><span data-stu-id="6a1f8-132">**Enable live response from the advanced settings page**.</span></span><br>
<span data-ttu-id="6a1f8-133">U moet de mogelijkheid voor livereactie inschakelen op de [pagina Instellingen voor geavanceerde](advanced-features.md) functies.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-133">You'll need to enable the live response capability in the [Advanced features settings](advanced-features.md) page.</span></span>

    >[!NOTE]
    ><span data-ttu-id="6a1f8-134">Alleen gebruikers met beveiligings- of globale beheerdersrollen kunnen deze instellingen bewerken.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-134">Only users with manage security or global admin roles can edit these settings.</span></span>

- <span data-ttu-id="6a1f8-135">**Schakel livereactie voor servers in vanaf de pagina met geavanceerde instellingen** (aanbevolen).</span><span class="sxs-lookup"><span data-stu-id="6a1f8-135">**Enable live response for servers from the advanced settings page** (recommended).</span></span><br>

    >[!NOTE]
    ><span data-ttu-id="6a1f8-136">Alleen gebruikers met beveiligings- of globale beheerdersrollen kunnen deze instellingen bewerken.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-136">Only users with manage security or global admin roles can edit these settings.</span></span>
    
- <span data-ttu-id="6a1f8-137">**Controleer of aan het apparaat een automatiseringssaneringsniveau is toegewezen.**</span><span class="sxs-lookup"><span data-stu-id="6a1f8-137">**Ensure that the device has an Automation Remediation level assigned to it**.</span></span><br>
<span data-ttu-id="6a1f8-138">U moet ten minste het minimale herstelniveau voor een bepaalde apparaatgroep inschakelen.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-138">You'll need to enable, at least, the minimum Remediation Level for a given Device Group.</span></span> <span data-ttu-id="6a1f8-139">Anders kunt u geen livereactiesessie voor een lid van die groep opzetten.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-139">Otherwise you won't be able to establish a Live Response session to a member of that group.</span></span>

    <span data-ttu-id="6a1f8-140">U krijgt de volgende foutmelding:</span><span class="sxs-lookup"><span data-stu-id="6a1f8-140">You'll receive the following error:</span></span>

    ![Afbeelding van foutbericht](images/live-response-error.png)

- <span data-ttu-id="6a1f8-142">**Live response unsigned script execution (optioneel)** inschakelen.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-142">**Enable live response unsigned script execution** (optional).</span></span> <br>

    >[!WARNING]
    ><span data-ttu-id="6a1f8-143">Als u het gebruik van niet-ondertekende scripts toestaat, kunt u uw blootstelling aan bedreigingen vergroten.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-143">Allowing the use of unsigned scripts may increase your exposure to threats.</span></span>
 
  <span data-ttu-id="6a1f8-144">Het uitvoeren van niet-ondertekende scripts wordt afgeraden, omdat dit uw blootstelling aan bedreigingen kan vergroten.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-144">Running unsigned scripts is not recommended as it can increase your exposure to threats.</span></span> <span data-ttu-id="6a1f8-145">Als u deze echter moet gebruiken, moet u de instelling inschakelen op de pagina Geavanceerde [functiesinstellingen.](advanced-features.md)</span><span class="sxs-lookup"><span data-stu-id="6a1f8-145">If you must use them however, you'll need to enable the setting in the [Advanced features settings](advanced-features.md) page.</span></span>
    
- <span data-ttu-id="6a1f8-146">**Controleer of u de juiste machtigingen hebt.**</span><span class="sxs-lookup"><span data-stu-id="6a1f8-146">**Ensure that you have the appropriate permissions**.</span></span><br>
    <span data-ttu-id="6a1f8-147">Alleen gebruikers die zijn ingericht met de juiste machtigingen, kunnen een sessie starten.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-147">Only users who have been provisioned with the appropriate permissions can initiate a session.</span></span> <span data-ttu-id="6a1f8-148">Zie Rollen maken en beheren voor meer informatie over [roltoewijzingen.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="6a1f8-148">For more information on role assignments, see [Create and manage roles](user-roles.md).</span></span> 

    > [!IMPORTANT]
    > <span data-ttu-id="6a1f8-149">De optie om een bestand te uploaden naar de bibliotheek is alleen beschikbaar voor personen met de juiste RBAC-machtigingen.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-149">The option to upload a file to the library is only available to those with the appropriate RBAC permissions.</span></span> <span data-ttu-id="6a1f8-150">De knop is grijs voor gebruikers met alleen gedelegeerde machtigingen.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-150">The button is greyed out for users with only delegated permissions.</span></span>

    <span data-ttu-id="6a1f8-151">Afhankelijk van de rol die aan u is verleend, kunt u eenvoudige of geavanceerde opdrachten voor livereacties uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-151">Depending on the role that's been granted to you, you can run basic or advanced live response commands.</span></span> <span data-ttu-id="6a1f8-152">Gebruikersmachtigingen worden bepaald door de aangepaste rol van RBAC.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-152">Users permissions are controlled by RBAC custom role.</span></span> 

## <a name="live-response-dashboard-overview"></a><span data-ttu-id="6a1f8-153">Overzicht van livereactiedashboard</span><span class="sxs-lookup"><span data-stu-id="6a1f8-153">Live response dashboard overview</span></span>
<span data-ttu-id="6a1f8-154">Wanneer u een livereactiesessie start op een apparaat, wordt er een dashboard geopend.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-154">When you initiate a live response session on a device, a dashboard opens.</span></span> <span data-ttu-id="6a1f8-155">Het dashboard bevat informatie over de sessie, zoals de volgende:</span><span class="sxs-lookup"><span data-stu-id="6a1f8-155">The dashboard provides information about the session such as the following:</span></span> 

- <span data-ttu-id="6a1f8-156">Wie de sessie gemaakt</span><span class="sxs-lookup"><span data-stu-id="6a1f8-156">Who created the session</span></span>
- <span data-ttu-id="6a1f8-157">Wanneer de sessie is gestart</span><span class="sxs-lookup"><span data-stu-id="6a1f8-157">When the session started</span></span>
- <span data-ttu-id="6a1f8-158">De duur van de sessie</span><span class="sxs-lookup"><span data-stu-id="6a1f8-158">The duration of the session</span></span>

<span data-ttu-id="6a1f8-159">Het dashboard biedt u ook toegang tot:</span><span class="sxs-lookup"><span data-stu-id="6a1f8-159">The dashboard also gives you access to:</span></span>
- <span data-ttu-id="6a1f8-160">Sessie verbreken</span><span class="sxs-lookup"><span data-stu-id="6a1f8-160">Disconnect session</span></span>
- <span data-ttu-id="6a1f8-161">Upload bestanden naar de bibliotheek</span><span class="sxs-lookup"><span data-stu-id="6a1f8-161">Upload files to the library</span></span> 
- <span data-ttu-id="6a1f8-162">Opdrachtconsole</span><span class="sxs-lookup"><span data-stu-id="6a1f8-162">Command console</span></span>
- <span data-ttu-id="6a1f8-163">Opdrachtlogboek</span><span class="sxs-lookup"><span data-stu-id="6a1f8-163">Command log</span></span>


## <a name="initiate-a-live-response-session-on-a-device"></a><span data-ttu-id="6a1f8-164">Een livereactiesessie starten op een apparaat</span><span class="sxs-lookup"><span data-stu-id="6a1f8-164">Initiate a live response session on a device</span></span> 

1. <span data-ttu-id="6a1f8-165">Meld u aan bij Microsoft Defender-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-165">Sign in to Microsoft Defender Security Center.</span></span>

2. <span data-ttu-id="6a1f8-166">Ga naar de pagina apparatenlijst en selecteer een apparaat dat u wilt onderzoeken.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-166">Navigate to the devices list page and select a device to investigate.</span></span> <span data-ttu-id="6a1f8-167">De pagina Apparaten wordt geopend.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-167">The devices page opens.</span></span>

3. <span data-ttu-id="6a1f8-168">Start de livereactiesessie door **Livereactiesessie starten te selecteren.**</span><span class="sxs-lookup"><span data-stu-id="6a1f8-168">Launch the live response session by selecting **Initiate live response session**.</span></span> <span data-ttu-id="6a1f8-169">Er wordt een opdrachtconsole weergegeven.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-169">A command console is displayed.</span></span> <span data-ttu-id="6a1f8-170">Wacht totdat de sessie verbinding maakt met het apparaat.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-170">Wait while the session connects to the device.</span></span>

4. <span data-ttu-id="6a1f8-171">Gebruik de ingebouwde opdrachten om onderzoekswerk te doen.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-171">Use the built-in commands to do investigative work.</span></span> <span data-ttu-id="6a1f8-172">Zie [Live-antwoordopdrachten voor meer informatie.](#live-response-commands)</span><span class="sxs-lookup"><span data-stu-id="6a1f8-172">For more information, see [Live response commands](#live-response-commands).</span></span>

5. <span data-ttu-id="6a1f8-173">Nadat u het onderzoek hebt afgerond, **selecteert** u Sessie verbreken en selecteert u **Bevestigen**.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-173">After completing your investigation, select **Disconnect session**, then select **Confirm**.</span></span>

## <a name="live-response-commands"></a><span data-ttu-id="6a1f8-174">Opdrachten voor livereacties</span><span class="sxs-lookup"><span data-stu-id="6a1f8-174">Live response commands</span></span>

<span data-ttu-id="6a1f8-175">Afhankelijk van de rol die aan u is verleend, kunt u eenvoudige of geavanceerde opdrachten voor livereacties uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-175">Depending on the role that's been granted to you, you can run basic or advanced live response commands.</span></span> <span data-ttu-id="6a1f8-176">Gebruikersmachtigingen worden beheerd door aangepaste rollen van RBAC.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-176">User permissions are controlled by RBAC custom roles.</span></span> <span data-ttu-id="6a1f8-177">Zie Rollen maken en beheren voor meer informatie over [roltoewijzingen.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="6a1f8-177">For more information on role assignments, see [Create and manage roles](user-roles.md).</span></span> 


>[!NOTE]
><span data-ttu-id="6a1f8-178">Live response is een interactieve shell in de cloud, dus specifieke opdrachtervaring kan variëren in reactietijd, afhankelijk van de netwerkkwaliteit en de systeembelasting tussen de eindgebruiker en het doelapparaat.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-178">Live response is a cloud-based interactive shell, as such, specific command experience may vary in response time depending on network quality and system load between the end user and the target device.</span></span>

### <a name="basic-commands"></a><span data-ttu-id="6a1f8-179">Basisopdrachten</span><span class="sxs-lookup"><span data-stu-id="6a1f8-179">Basic commands</span></span>

<span data-ttu-id="6a1f8-180">De volgende opdrachten zijn beschikbaar voor gebruikersrollen die de mogelijkheid krijgen om basisopdrachten **voor** livereacties uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-180">The following commands are available for user roles that are granted the ability to run **basic** live response commands.</span></span> <span data-ttu-id="6a1f8-181">Zie Rollen maken en beheren voor meer informatie over [roltoewijzingen.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="6a1f8-181">For more information on role assignments, see [Create and manage roles](user-roles.md).</span></span> 

| <span data-ttu-id="6a1f8-182">Opdracht</span><span class="sxs-lookup"><span data-stu-id="6a1f8-182">Command</span></span> | <span data-ttu-id="6a1f8-183">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="6a1f8-183">Description</span></span> |
|---|---|--- |
|`cd` | <span data-ttu-id="6a1f8-184">Wijzigt de huidige adreslijst.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-184">Changes the current directory.</span></span> | 
|`cls` | <span data-ttu-id="6a1f8-185">Het scherm van de console wordt gewed.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-185">Clears the console screen.</span></span>  |
|`connect` | <span data-ttu-id="6a1f8-186">Start een livereactiesessie op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-186">Initiates a live response session to the device.</span></span> |
|`connections` | <span data-ttu-id="6a1f8-187">Toont alle actieve verbindingen.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-187">Shows all the active connections.</span></span> |
|`dir` | <span data-ttu-id="6a1f8-188">Toont een lijst met bestanden en subdirectorieën in een adreslijst.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-188">Shows a list of files and subdirectories in a directory.</span></span> |
|`drivers` |  <span data-ttu-id="6a1f8-189">Toont alle stuurprogramma's die op het apparaat zijn geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-189">Shows all drivers installed on the device.</span></span> |
|`fg <command ID>` | <span data-ttu-id="6a1f8-190">Plaats de opgegeven taak op de voorgrond op de voorgrond, zodat deze de huidige taak is.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-190">Place the specified job in the foreground in the foreground, making it the current job.</span></span> <br> <span data-ttu-id="6a1f8-191">OPMERKING: fg gebruikt een 'opdracht-id' die beschikbaar is vanuit taken, niet uit een PID</span><span class="sxs-lookup"><span data-stu-id="6a1f8-191">NOTE: fg takes a “command ID” available from jobs, not a PID</span></span> |
|`fileinfo` | <span data-ttu-id="6a1f8-192">Informatie over een bestand.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-192">Get information about a file.</span></span> |
|`findfile` | <span data-ttu-id="6a1f8-193">Zoekt bestanden op een bepaalde naam op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-193">Locates files by a given name on the device.</span></span> |
|`getfile <file_path>` | <span data-ttu-id="6a1f8-194">Hiermee wordt een bestand gedownload.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-194">Downloads a file.</span></span> |
|`help` | <span data-ttu-id="6a1f8-195">Biedt help-informatie voor opdrachten voor livereacties.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-195">Provides help information for live response commands.</span></span> |
|`jobs` | <span data-ttu-id="6a1f8-196">Toont momenteel lopende taken, hun id en status.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-196">Shows currently running jobs, their ID and status.</span></span> |
|`persistence` | <span data-ttu-id="6a1f8-197">Toont alle bekende persistentiemethoden op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-197">Shows all known persistence methods on the device.</span></span> |
|`processes` | <span data-ttu-id="6a1f8-198">Toont alle processen die op het apparaat worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-198">Shows all processes running on the device.</span></span> |
|`registry` | <span data-ttu-id="6a1f8-199">Geeft registerwaarden weer.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-199">Shows registry values.</span></span> |
|`scheduledtasks` | <span data-ttu-id="6a1f8-200">Toont alle geplande taken op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-200">Shows all scheduled tasks on the device.</span></span> |
|`services` | <span data-ttu-id="6a1f8-201">Toont alle services op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-201">Shows all services on the device.</span></span> |
|`trace` | <span data-ttu-id="6a1f8-202">Hiermee stelt u de logboekregistratiemodus van de terminal in op foutopsporing.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-202">Sets the terminal's logging mode to debug.</span></span> |

### <a name="advanced-commands"></a><span data-ttu-id="6a1f8-203">Geavanceerde opdrachten</span><span class="sxs-lookup"><span data-stu-id="6a1f8-203">Advanced commands</span></span>
<span data-ttu-id="6a1f8-204">De volgende opdrachten zijn beschikbaar voor gebruikersrollen die de mogelijkheid krijgen om geavanceerde **opdrachten** voor livereacties uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-204">The following commands are available for user roles that are granted the ability to run **advanced** live response commands.</span></span> <span data-ttu-id="6a1f8-205">Zie Rollen maken en beheren voor meer informatie over [roltoewijzingen.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="6a1f8-205">For more information on role assignments, see [Create and manage roles](user-roles.md).</span></span> 

| <span data-ttu-id="6a1f8-206">Opdracht</span><span class="sxs-lookup"><span data-stu-id="6a1f8-206">Command</span></span> | <span data-ttu-id="6a1f8-207">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="6a1f8-207">Description</span></span> |
|---|---|
| `analyze` | <span data-ttu-id="6a1f8-208">Analyseert de entiteit met verschillende belastende motoren om tot een uitspraak te komen.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-208">Analyses the entity with various incrimination engines to reach a verdict.</span></span> |
| `run` | <span data-ttu-id="6a1f8-209">Voert een PowerShell-script uit vanuit de bibliotheek op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-209">Runs a PowerShell script from the library on the device.</span></span> |
| `library` | <span data-ttu-id="6a1f8-210">Hiermee worden bestanden vermeld die zijn geüpload naar de live antwoordbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-210">Lists files that were uploaded to the live response library.</span></span> |
| `putfile` | <span data-ttu-id="6a1f8-211">Zet een bestand uit de bibliotheek op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-211">Puts a file from the library to the device.</span></span> <span data-ttu-id="6a1f8-212">Bestanden worden opgeslagen in een werkmap en worden verwijderd wanneer het apparaat standaard opnieuw wordt gestart.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-212">Files are saved in a working folder and are deleted when the device restarts by default.</span></span> |
| `remediate` | <span data-ttu-id="6a1f8-213">Herstelt een entiteit op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-213">Remediates an entity on the device.</span></span> <span data-ttu-id="6a1f8-214">De herstelactie is afhankelijk van het entiteitstype:</span><span class="sxs-lookup"><span data-stu-id="6a1f8-214">The remediation action will vary depending on the entity type:</span></span><br><span data-ttu-id="6a1f8-215">- Bestand: verwijderen</span><span class="sxs-lookup"><span data-stu-id="6a1f8-215">- File: delete</span></span><br><span data-ttu-id="6a1f8-216">- Proces: stoppen, afbeeldingsbestand verwijderen</span><span class="sxs-lookup"><span data-stu-id="6a1f8-216">- Process: stop, delete image file</span></span><br><span data-ttu-id="6a1f8-217">- Service: stoppen, afbeeldingsbestand verwijderen</span><span class="sxs-lookup"><span data-stu-id="6a1f8-217">- Service: stop, delete image file</span></span><br><span data-ttu-id="6a1f8-218">- Registerinvoer: verwijderen</span><span class="sxs-lookup"><span data-stu-id="6a1f8-218">- Registry entry: delete</span></span><br><span data-ttu-id="6a1f8-219">- Geplande taak: verwijderen</span><span class="sxs-lookup"><span data-stu-id="6a1f8-219">- Scheduled task: remove</span></span><br><span data-ttu-id="6a1f8-220">- Mapitem opstarten: bestand verwijderen</span><span class="sxs-lookup"><span data-stu-id="6a1f8-220">- Startup folder item: delete file</span></span> <br> <span data-ttu-id="6a1f8-221">OPMERKING: Deze opdracht heeft een vereiste opdracht.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-221">NOTE: This command has a prerequisite command.</span></span> <span data-ttu-id="6a1f8-222">U kunt de opdracht in combinatie met de opdracht gebruiken `-auto` om de vereiste opdracht automatisch uit te `remediate` voeren.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-222">You can use the `-auto` command in conjunction with `remediate` to automatically run the prerequisite command.</span></span> 
|`undo` | <span data-ttu-id="6a1f8-223">Herstelt een entiteit die is hersteld.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-223">Restores an entity that was remediated.</span></span> |


## <a name="use-live-response-commands"></a><span data-ttu-id="6a1f8-224">Opdrachten voor livereacties gebruiken</span><span class="sxs-lookup"><span data-stu-id="6a1f8-224">Use live response commands</span></span>

<span data-ttu-id="6a1f8-225">De opdrachten die u in de console kunt gebruiken, volgen dezelfde principes als [Windows Opdrachten.](/windows-server/administration/windows-commands/windows-commands#BKMK_c)</span><span class="sxs-lookup"><span data-stu-id="6a1f8-225">The commands that you can use in the console follow similar principles as [Windows Commands](/windows-server/administration/windows-commands/windows-commands#BKMK_c).</span></span>

<span data-ttu-id="6a1f8-226">De geavanceerde opdrachten bieden een krachtigere reeks acties waarmee u krachtigere acties kunt uitvoeren, zoals het downloaden en uploaden van een bestand, het uitvoeren van scripts op het apparaat en het uitvoeren van herstelacties voor een entiteit.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-226">The advanced commands offer a more robust set of actions that allow you to take more powerful actions such as download and upload a file, run scripts on the device, and take remediation actions on an entity.</span></span>

### <a name="get-a-file-from-the-device"></a><span data-ttu-id="6a1f8-227">Een bestand van het apparaat downloaden</span><span class="sxs-lookup"><span data-stu-id="6a1f8-227">Get a file from the device</span></span>

<span data-ttu-id="6a1f8-228">Voor scenario's wanneer u een bestand wilt downloaden van een apparaat dat u onderzoekt, kunt u de opdracht `getfile` gebruiken.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-228">For scenarios when you'd like get a file from a device you're investigating, you can use the `getfile` command.</span></span> <span data-ttu-id="6a1f8-229">Hiermee kunt u het bestand opslaan vanaf het apparaat voor verder onderzoek.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-229">This allows you to save the file from the device for further investigation.</span></span>

>[!NOTE]
><span data-ttu-id="6a1f8-230">De volgende limieten voor bestandsgrootte zijn van toepassing:</span><span class="sxs-lookup"><span data-stu-id="6a1f8-230">The following file size limits apply:</span></span>
>- <span data-ttu-id="6a1f8-231">`getfile` limiet: 3 GB</span><span class="sxs-lookup"><span data-stu-id="6a1f8-231">`getfile` limit: 3 GB</span></span>
>- <span data-ttu-id="6a1f8-232">`fileinfo` limiet: 10 GB</span><span class="sxs-lookup"><span data-stu-id="6a1f8-232">`fileinfo` limit: 10 GB</span></span>
>- <span data-ttu-id="6a1f8-233">`library` limiet: 250 MB</span><span class="sxs-lookup"><span data-stu-id="6a1f8-233">`library` limit: 250 MB</span></span>

### <a name="download-a-file-in-the-background"></a><span data-ttu-id="6a1f8-234">Een bestand op de achtergrond downloaden</span><span class="sxs-lookup"><span data-stu-id="6a1f8-234">Download a file in the background</span></span>

<span data-ttu-id="6a1f8-235">Als u wilt dat uw beveiligingsteam een beïnvloed apparaat kan blijven onderzoeken, kunnen bestanden nu op de achtergrond worden gedownload.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-235">To enable your security operations team to continue investigating an impacted device, files can now be downloaded in the background.</span></span>

- <span data-ttu-id="6a1f8-236">Als u een bestand op de achtergrond wilt downloaden, typt u in de opdrachtconsole voor `download <file_path> &` livereactie.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-236">To download a file in the background, in the live response command console, type `download <file_path> &`.</span></span>
- <span data-ttu-id="6a1f8-237">Als u wacht totdat een bestand wordt gedownload, kunt u het naar de achtergrond verplaatsen met Ctrl+ Z.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-237">If you are waiting for a file to be downloaded, you can move it to the background by using Ctrl + Z.</span></span>
- <span data-ttu-id="6a1f8-238">Als u een bestand wilt downloaden naar de voorgrond, typt u in de opdrachtconsole voor `fg <command_id>` livereactie.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-238">To bring a file download to the foreground, in the live response command console, type `fg <command_id>`.</span></span>

<span data-ttu-id="6a1f8-239">Dit zijn enkele voorbeelden:</span><span class="sxs-lookup"><span data-stu-id="6a1f8-239">Here are some examples:</span></span>


|<span data-ttu-id="6a1f8-240">Opdracht</span><span class="sxs-lookup"><span data-stu-id="6a1f8-240">Command</span></span>  |<span data-ttu-id="6a1f8-241">Wat het doet</span><span class="sxs-lookup"><span data-stu-id="6a1f8-241">What it does</span></span>  |
|---------|---------|
|`getfile "C:\windows\some_file.exe" &`     |<span data-ttu-id="6a1f8-242">Start het downloaden van een bestand met *some_file.exe* op de achtergrond.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-242">Starts downloading a file named *some_file.exe* in the background.</span></span>         |
|`fg 1234`     |<span data-ttu-id="6a1f8-243">Retourneert een download met *opdracht-id 1234* op de voorgrond.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-243">Returns a download with command ID *1234* to the foreground.</span></span>         |


### <a name="put-a-file-in-the-library"></a><span data-ttu-id="6a1f8-244">Een bestand in de bibliotheek zetten</span><span class="sxs-lookup"><span data-stu-id="6a1f8-244">Put a file in the library</span></span>

<span data-ttu-id="6a1f8-245">Live response heeft een bibliotheek waarin u bestanden kunt plaatsen.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-245">Live response has a library where you can put files into.</span></span> <span data-ttu-id="6a1f8-246">In de bibliotheek worden bestanden (zoals scripts) opgeslagen die kunnen worden uitgevoerd in een livereactiesessie op tenantniveau.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-246">The library stores files (such as scripts) that can be run in a live response session at the tenant level.</span></span>

<span data-ttu-id="6a1f8-247">Met livereactie kunnen PowerShell-scripts worden uitgevoerd, maar u moet de bestanden eerst in de bibliotheek zetten voordat u ze kunt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-247">Live response allows PowerShell scripts to run, however you must first put the files into the library before you can run them.</span></span> 

<span data-ttu-id="6a1f8-248">U kunt een verzameling PowerShell-scripts hebben die kunnen worden uitgevoerd op apparaten met wie u livereactiesessies start.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-248">You can have a collection of PowerShell scripts that can run on devices that you initiate live response sessions with.</span></span> 

#### <a name="to-upload-a-file-in-the-library"></a><span data-ttu-id="6a1f8-249">Een bestand uploaden in de bibliotheek</span><span class="sxs-lookup"><span data-stu-id="6a1f8-249">To upload a file in the library</span></span>

1. <span data-ttu-id="6a1f8-250">Klik **Upload bestand naar bibliotheek.**</span><span class="sxs-lookup"><span data-stu-id="6a1f8-250">Click **Upload file to library**.</span></span> 

2. <span data-ttu-id="6a1f8-251">Klik **op Bladeren** en selecteer het bestand.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-251">Click **Browse** and select the file.</span></span>

3. <span data-ttu-id="6a1f8-252">Geef een korte beschrijving op.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-252">Provide a brief description.</span></span>

4. <span data-ttu-id="6a1f8-253">Geef op of u een bestand met dezelfde naam wilt overschrijven.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-253">Specify if you'd like to overwrite a file with the same name.</span></span>

5. <span data-ttu-id="6a1f8-254">Als u wilt weten welke parameters nodig zijn voor het script, schakelt u het selectievakje scriptparameters in.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-254">If you'd like to be,  know what parameters are needed for the script, select the script parameters check box.</span></span> <span data-ttu-id="6a1f8-255">Voer in het tekstveld een voorbeeld en een beschrijving in.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-255">In the text field, enter an example and a description.</span></span>

6. <span data-ttu-id="6a1f8-256">Klik **op Bevestigen**.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-256">Click **Confirm**.</span></span> 

7. <span data-ttu-id="6a1f8-257">(Optioneel) Voer de opdracht uit om te controleren of het bestand naar de bibliotheek is `library` geüpload.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-257">(Optional) To verify that the file was uploaded to the library, run the `library` command.</span></span>


### <a name="cancel-a-command"></a><span data-ttu-id="6a1f8-258">Een opdracht annuleren</span><span class="sxs-lookup"><span data-stu-id="6a1f8-258">Cancel a command</span></span>
<span data-ttu-id="6a1f8-259">Op elk gewenst moment tijdens een sessie kunt u een opdracht annuleren door op Ctrl + C te drukken.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-259">Anytime during a session, you can cancel a command by pressing CTRL + C.</span></span>  

>[!WARNING]
><span data-ttu-id="6a1f8-260">Als u deze snelkoppeling gebruikt, stopt u de opdracht niet aan de agentzijde.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-260">Using this shortcut will not stop the command in the agent side.</span></span> <span data-ttu-id="6a1f8-261">De opdracht in de portal wordt alleen geannuleerd.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-261">It will only cancel the command in the portal.</span></span> <span data-ttu-id="6a1f8-262">Het wijzigen van bewerkingen zoals 'herstel' kan dus doorgaan, terwijl de opdracht wordt geannuleerd.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-262">So, changing operations such as "remediate" may continue, while the command is canceled.</span></span> 

## <a name="run-a-powershell-script"></a><span data-ttu-id="6a1f8-263">Een PowerShell-script uitvoeren</span><span class="sxs-lookup"><span data-stu-id="6a1f8-263">Run a PowerShell script</span></span> 

<span data-ttu-id="6a1f8-264">Voordat u een PowerShell-script kunt uitvoeren, moet u het eerst uploaden naar de bibliotheek.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-264">Before you can run a PowerShell script, you must first upload it to the library.</span></span> 

<span data-ttu-id="6a1f8-265">Nadat u het script naar de bibliotheek hebt geüpload, gebruikt u de `run` opdracht om het script uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-265">After uploading the script to the library, use the `run` command to run the script.</span></span>

<span data-ttu-id="6a1f8-266">Als u van plan bent een niet-ondertekend script te gebruiken in de sessie, moet u de instelling inschakelen op de pagina Geavanceerde [functies instellingen.](advanced-features.md)</span><span class="sxs-lookup"><span data-stu-id="6a1f8-266">If you plan to use an unsigned script in the session, you'll need to enable the setting in the [Advanced features settings](advanced-features.md) page.</span></span>

>[!WARNING]
><span data-ttu-id="6a1f8-267">Als u het gebruik van niet-ondertekende scripts toestaat, kunt u uw blootstelling aan bedreigingen vergroten.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-267">Allowing the use of unsigned scripts may increase your exposure to threats.</span></span>

## <a name="apply-command-parameters"></a><span data-ttu-id="6a1f8-268">Opdrachtparameters toepassen</span><span class="sxs-lookup"><span data-stu-id="6a1f8-268">Apply command parameters</span></span>

- <span data-ttu-id="6a1f8-269">Bekijk de help van de console voor meer informatie over opdrachtparameters.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-269">View the console help to learn about command parameters.</span></span> <span data-ttu-id="6a1f8-270">Voer het volgende uit als u meer wilt weten over een afzonderlijke opdracht:</span><span class="sxs-lookup"><span data-stu-id="6a1f8-270">To learn about an individual command, run:</span></span>
 
    `help <command name>`

- <span data-ttu-id="6a1f8-271">Bij het toepassen van parameters op opdrachten, moet u er rekening mee houden dat parameters worden verwerkt op basis van een vaste volgorde:</span><span class="sxs-lookup"><span data-stu-id="6a1f8-271">When applying parameters to commands, note that parameters are handled based on a fixed order:</span></span>
 
    `<command name> param1 param2` 

- <span data-ttu-id="6a1f8-272">Wanneer u parameters opgeeft buiten de vaste volgorde, geeft u de naam van de parameter op met een afbreekstreester voordat u de waarde opgeeft:</span><span class="sxs-lookup"><span data-stu-id="6a1f8-272">When specifying parameters outside of the fixed order, specify the name of the parameter with a hyphen before providing the value:</span></span>
 
    `<command name> -param2_name param2`

- <span data-ttu-id="6a1f8-273">Wanneer u opdrachten gebruikt met vereiste opdrachten, kunt u vlaggen gebruiken:</span><span class="sxs-lookup"><span data-stu-id="6a1f8-273">When using commands that have prerequisite commands, you can use flags:</span></span>

    <span data-ttu-id="6a1f8-274">`<command name> -type file -id <file path> - auto` of `remediate file <file path> - auto` .</span><span class="sxs-lookup"><span data-stu-id="6a1f8-274">`<command name> -type file -id <file path> - auto` or `remediate file <file path> - auto`.</span></span>

## <a name="supported-output-types"></a><span data-ttu-id="6a1f8-275">Ondersteunde uitvoertypen</span><span class="sxs-lookup"><span data-stu-id="6a1f8-275">Supported output types</span></span>

<span data-ttu-id="6a1f8-276">Livereactie ondersteunt uitvoertypen voor tabel- en JSON-indeling.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-276">Live response supports table and JSON format output types.</span></span> <span data-ttu-id="6a1f8-277">Voor elke opdracht is er een standaarduitvoergedrag.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-277">For each command, there's a default output behavior.</span></span> <span data-ttu-id="6a1f8-278">U kunt de uitvoer in de gewenste uitvoerindeling wijzigen met de volgende opdrachten:</span><span class="sxs-lookup"><span data-stu-id="6a1f8-278">You can modify the output in your preferred output format using the following commands:</span></span>

- `-output json`
- `-output table`

>[!NOTE]
><span data-ttu-id="6a1f8-279">Er worden minder velden weergegeven in tabelindeling vanwege de beperkte ruimte.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-279">Fewer fields are shown in table format due to the limited space.</span></span> <span data-ttu-id="6a1f8-280">Als u meer details in de uitvoer wilt zien, kunt u de opdracht JSON-uitvoer gebruiken, zodat er meer details worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-280">To see more details in the output, you can use the JSON output command so that more details are shown.</span></span>

## <a name="supported-output-pipes"></a><span data-ttu-id="6a1f8-281">Ondersteunde uitvoerpijpen</span><span class="sxs-lookup"><span data-stu-id="6a1f8-281">Supported output pipes</span></span>

<span data-ttu-id="6a1f8-282">Live response ondersteunt uitvoerpijpleidingen naar CLI en bestand.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-282">Live response supports output piping to CLI and file.</span></span> <span data-ttu-id="6a1f8-283">CLI is het standaarduitvoergedrag.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-283">CLI is the default output behavior.</span></span> <span data-ttu-id="6a1f8-284">U kunt de uitvoer naar een bestand uitvoeren met de volgende opdracht: [command] > [bestandsnaam].txt.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-284">You can pipe the output to a file using the following command: [command] > [filename].txt.</span></span>  

<span data-ttu-id="6a1f8-285">Voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="6a1f8-285">Example:</span></span>

```console
processes > output.txt
```

## <a name="view-the-command-log"></a><span data-ttu-id="6a1f8-286">Het opdrachtlogboek weergeven</span><span class="sxs-lookup"><span data-stu-id="6a1f8-286">View the command log</span></span>

<span data-ttu-id="6a1f8-287">Selecteer het **tabblad Opdrachtlogboek** om de opdrachten weer te geven die tijdens een sessie op het apparaat zijn gebruikt.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-287">Select the **Command log** tab to see the commands used on the device during a session.</span></span> <span data-ttu-id="6a1f8-288">Elke opdracht wordt bijgespoord met volledige details, zoals:</span><span class="sxs-lookup"><span data-stu-id="6a1f8-288">Each command is tracked with full details such as:</span></span>
- <span data-ttu-id="6a1f8-289">ID</span><span class="sxs-lookup"><span data-stu-id="6a1f8-289">ID</span></span>
- <span data-ttu-id="6a1f8-290">Opdrachtregel</span><span class="sxs-lookup"><span data-stu-id="6a1f8-290">Command line</span></span>
- <span data-ttu-id="6a1f8-291">Duur</span><span class="sxs-lookup"><span data-stu-id="6a1f8-291">Duration</span></span>
- <span data-ttu-id="6a1f8-292">Status- en invoer- of uitvoerzijdebalk</span><span class="sxs-lookup"><span data-stu-id="6a1f8-292">Status and input or output side bar</span></span>

## <a name="limitations"></a><span data-ttu-id="6a1f8-293">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="6a1f8-293">Limitations</span></span>

- <span data-ttu-id="6a1f8-294">Livereactiesessies zijn beperkt tot 25 livereactiesessies tegelijk.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-294">Live response sessions are limited to 25 live response sessions at a time.</span></span>
- <span data-ttu-id="6a1f8-295">De inactieve time-outwaarde voor livereactiesessie is 30 minuten.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-295">Live response session inactive timeout value is 30 minutes.</span></span> 
- <span data-ttu-id="6a1f8-296">Een gebruiker kan maximaal tien gelijktijdige sessies starten.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-296">A user can initiate up to 10 concurrent sessions.</span></span>
- <span data-ttu-id="6a1f8-297">Een apparaat kan slechts in één sessie tegelijk worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="6a1f8-297">A device can only be in one session at a time.</span></span>
- <span data-ttu-id="6a1f8-298">De volgende limieten voor bestandsgrootte zijn van toepassing:</span><span class="sxs-lookup"><span data-stu-id="6a1f8-298">The following file size limits apply:</span></span>
   - <span data-ttu-id="6a1f8-299">`getfile` limiet: 3 GB</span><span class="sxs-lookup"><span data-stu-id="6a1f8-299">`getfile` limit: 3 GB</span></span>
   - <span data-ttu-id="6a1f8-300">`fileinfo` limiet: 10 GB</span><span class="sxs-lookup"><span data-stu-id="6a1f8-300">`fileinfo` limit: 10 GB</span></span>
   - <span data-ttu-id="6a1f8-301">`library` limiet: 250 MB</span><span class="sxs-lookup"><span data-stu-id="6a1f8-301">`library` limit: 250 MB</span></span>

## <a name="related-article"></a><span data-ttu-id="6a1f8-302">Gerelateerd artikel</span><span class="sxs-lookup"><span data-stu-id="6a1f8-302">Related article</span></span>
- [<span data-ttu-id="6a1f8-303">Voorbeelden van opdrachten voor Live-reacties</span><span class="sxs-lookup"><span data-stu-id="6a1f8-303">Live response command examples</span></span>](live-response-command-examples.md)
