---
title: Belangrijke mappen beschermen tegen ransomware tegen het versleutelen van uw bestanden met gecontroleerde maptoegang
description: Bestanden in standaardmappen kunnen worden beveiligd tegen het wijzigen van schadelijke apps. Voorkom dat ransomware uw bestanden versleutelt.
keywords: gecontroleerde maptoegang, windows 10, Windows Defender, ransomware, beveiligen, bestanden, mappen
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
audience: ITPro
ms.date: 02/03/2021
ms.reviewer: v-maave
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: b937dd41f0296f2cf4102f41f8ab10bd55e1c35d
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51200279"
---
# <a name="protect-important-folders-with-controlled-folder-access"></a><span data-ttu-id="208b3-105">Belangrijke mappen beveiligen met gecontroleerde maptoegang</span><span class="sxs-lookup"><span data-stu-id="208b3-105">Protect important folders with controlled folder access</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="208b3-106">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="208b3-106">**Applies to:**</span></span>
- [<span data-ttu-id="208b3-107">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="208b3-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="208b3-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="208b3-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="208b3-109">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="208b3-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="208b3-110">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="208b3-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-controlled-folder-access"></a><span data-ttu-id="208b3-111">Wat is beheerde maptoegang?</span><span class="sxs-lookup"><span data-stu-id="208b3-111">What is controlled folder access?</span></span>

<span data-ttu-id="208b3-112">Gecontroleerde maptoegang helpt uw waardevolle gegevens te beschermen tegen schadelijke apps en bedreigingen, zoals ransomware.</span><span class="sxs-lookup"><span data-stu-id="208b3-112">Controlled folder access helps protect your valuable data from malicious apps and threats, such as ransomware.</span></span> <span data-ttu-id="208b3-113">Gecontroleerde maptoegang beschermt uw gegevens door apps te controleren op een lijst met bekende, vertrouwde apps.</span><span class="sxs-lookup"><span data-stu-id="208b3-113">Controlled folder access protects your data by checking apps against a list of known, trusted apps.</span></span> <span data-ttu-id="208b3-114">Beheerde maptoegang wordt ondersteund op Windows Server 2019- en Windows 10-clients en kan worden ingeschakeld met de Windows-beveiligingsapp, Microsoft Endpoint Configuration Manager of Intune (voor beheerde apparaten).</span><span class="sxs-lookup"><span data-stu-id="208b3-114">Supported on Windows Server 2019 and Windows 10 clients, controlled folder access can be turned on using the Windows Security App, Microsoft Endpoint Configuration Manager, or Intune (for managed devices).</span></span> 

> [!NOTE]
> <span data-ttu-id="208b3-115">Scripting-engines worden niet vertrouwd en u kunt ze geen toegang verlenen tot gecontroleerde beveiligde mappen.</span><span class="sxs-lookup"><span data-stu-id="208b3-115">Scripting engines are not trusted and you cannot allow them access to controlled protected folders.</span></span>  <span data-ttu-id="208b3-116">PowerShell wordt bijvoorbeeld niet vertrouwd door gecontroleerde maptoegang, zelfs niet als u dit toestaat met [certificaat- en bestandsindicatoren.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/indicator-certificates)</span><span class="sxs-lookup"><span data-stu-id="208b3-116">For example, PowerShell is not trusted by controlled folder access, even if you allow with [certificate and file indicators](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/indicator-certificates).</span></span> 

<span data-ttu-id="208b3-117">Gecontroleerde toegang tot mappen werkt het beste met [Microsoft Defender voor](microsoft-defender-endpoint.md)Eindpunt, waarmee u gedetailleerde rapportage krijgt over gebeurtenissen en blokken voor gecontroleerde mappentoegang als onderdeel van de gebruikelijke scenario's voor [waarschuwingsonderzoek.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="208b3-117">Controlled folder access works best with [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md), which gives you detailed reporting into controlled folder access events and blocks as part of the usual [alert investigation scenarios](investigate-alerts.md).</span></span>

> [!TIP]
> <span data-ttu-id="208b3-118">Met gecontroleerde mappentoegangsblokken worden geen waarschuwingen gegenereerd in de [wachtrij Waarschuwingen.](alerts-queue.md)</span><span class="sxs-lookup"><span data-stu-id="208b3-118">Controlled folder access blocks don't generate alerts in the [Alerts queue](alerts-queue.md).</span></span> <span data-ttu-id="208b3-119">U kunt echter informatie over beheerde maptoegangsblokken weergeven in de tijdlijnweergave van het [apparaat,](investigate-machines.md)tijdens het gebruik van geavanceerd zoeken [of](advanced-hunting-overview.md)met [aangepaste detectieregels.](custom-detection-rules.md)</span><span class="sxs-lookup"><span data-stu-id="208b3-119">However, you can view information about controlled folder access blocks in the [device timeline view](investigate-machines.md), while using [advanced hunting](advanced-hunting-overview.md), or with [custom detection rules](custom-detection-rules.md).</span></span>

## <a name="how-does-controlled-folder-access-work"></a><span data-ttu-id="208b3-120">Hoe werkt beheerde maptoegang?</span><span class="sxs-lookup"><span data-stu-id="208b3-120">How does controlled folder access work?</span></span>

<span data-ttu-id="208b3-121">Gecontroleerde maptoegang werkt door alleen vertrouwde apps toegang te geven tot beveiligde mappen.</span><span class="sxs-lookup"><span data-stu-id="208b3-121">Controlled folder access works by only allowing trusted apps to access protected folders.</span></span> <span data-ttu-id="208b3-122">Beveiligde mappen worden opgegeven wanneer beheerde maptoegang is geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="208b3-122">Protected folders are specified when controlled folder access is configured.</span></span> <span data-ttu-id="208b3-123">Meestal worden veelgebruikte mappen, zoals mappen die worden gebruikt voor documenten, afbeeldingen, downloads, en dergelijke, opgenomen in de lijst met beheerde mappen.</span><span class="sxs-lookup"><span data-stu-id="208b3-123">Typically, commonly used folders, such as those used for documents, pictures, downloads, and so on, are included in the list of controlled folders.</span></span> 

<span data-ttu-id="208b3-124">Gecontroleerde maptoegang werkt met een lijst met vertrouwde apps.</span><span class="sxs-lookup"><span data-stu-id="208b3-124">Controlled folder access works with a list of trusted apps.</span></span> <span data-ttu-id="208b3-125">Apps die zijn opgenomen in de lijst met vertrouwde software werken zoals verwacht.</span><span class="sxs-lookup"><span data-stu-id="208b3-125">Apps that are included in the list of trusted software work as expected.</span></span> <span data-ttu-id="208b3-126">Apps die niet in de lijst zijn opgenomen, kunnen geen wijzigingen aanbrengen in bestanden in beveiligde mappen.</span><span class="sxs-lookup"><span data-stu-id="208b3-126">Apps that are not included in the list are prevented from making any changes to files inside protected folders.</span></span> 

<span data-ttu-id="208b3-127">Apps worden toegevoegd aan de lijst op basis van hun aanwezigheid en reputatie.</span><span class="sxs-lookup"><span data-stu-id="208b3-127">Apps are added to the list based upon their prevalence and reputation.</span></span> <span data-ttu-id="208b3-128">Apps die veel voorkomen in uw organisatie en die nooit gedrag hebben weergegeven dat als schadelijk wordt beschouwd, worden als betrouwbaar beschouwd.</span><span class="sxs-lookup"><span data-stu-id="208b3-128">Apps that are highly prevalent throughout your organization and that have never displayed any behavior deemed malicious are considered trustworthy.</span></span> <span data-ttu-id="208b3-129">Deze apps worden automatisch aan de lijst toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="208b3-129">Those apps are added to the list automatically.</span></span>

<span data-ttu-id="208b3-130">Apps kunnen ook handmatig worden toegevoegd aan de vertrouwde lijst met Behulp van Configuration Manager of Intune.</span><span class="sxs-lookup"><span data-stu-id="208b3-130">Apps can also be added manually to the trusted list by using Configuration Manager or Intune.</span></span> <span data-ttu-id="208b3-131">Extra acties, zoals het [toevoegen van een bestandsindicator](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file) voor een app, kunnen worden uitgevoerd vanuit de console van het beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="208b3-131">Additional actions, such as [adding a file indicator](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file) for an app, can be performed from the Security Center Console.</span></span>

## <a name="why-controlled-folder-access-is-important"></a><span data-ttu-id="208b3-132">Waarom gecontroleerde maptoegang belangrijk is</span><span class="sxs-lookup"><span data-stu-id="208b3-132">Why controlled folder access is important</span></span>

<span data-ttu-id="208b3-133">Gecontroleerde toegang tot mappen is vooral handig om uw documenten en informatie te beschermen tegen [ransomware.](https://www.microsoft.com/wdsi/threats/ransomware)</span><span class="sxs-lookup"><span data-stu-id="208b3-133">Controlled folder access is especially useful in helping to protect your documents and information from [ransomware](https://www.microsoft.com/wdsi/threats/ransomware).</span></span> <span data-ttu-id="208b3-134">Bij een ransomware-aanval kunnen uw bestanden worden versleuteld en gegijzeld.</span><span class="sxs-lookup"><span data-stu-id="208b3-134">In a ransomware attack, your files can get encrypted and held hostage.</span></span> <span data-ttu-id="208b3-135">Er wordt een melding weergegeven op de computer waarop een app heeft geprobeerd wijzigingen aan te brengen in een bestand in een beveiligde map.</span><span class="sxs-lookup"><span data-stu-id="208b3-135">With controlled folder access in place, a notification appears on the computer where an app attempted to make changes to a file in a protected folder.</span></span> <span data-ttu-id="208b3-136">U kunt [de melding aanpassen met](customize-attack-surface-reduction.md#customize-the-notification) uw bedrijfsgegevens en contactgegevens.</span><span class="sxs-lookup"><span data-stu-id="208b3-136">You can [customize the notification](customize-attack-surface-reduction.md#customize-the-notification) with your company details and contact information.</span></span> <span data-ttu-id="208b3-137">U kunt de regels ook afzonderlijk inschakelen om aan te passen welke technieken de functiemonitors heeft.</span><span class="sxs-lookup"><span data-stu-id="208b3-137">You can also enable the rules individually to customize what techniques the feature monitors.</span></span>

<span data-ttu-id="208b3-138">De [beveiligde mappen bevatten](#review-controlled-folder-access-events-in-windows-event-viewer) veelgebruikte systeemmappen (inclusief opstartsectoren) en u kunt meer mappen [toevoegen.](customize-controlled-folders.md#protect-additional-folders)</span><span class="sxs-lookup"><span data-stu-id="208b3-138">The [protected folders](#review-controlled-folder-access-events-in-windows-event-viewer) include common system folders (including boot sectors), and you can [add more folders](customize-controlled-folders.md#protect-additional-folders).</span></span> <span data-ttu-id="208b3-139">U kunt ook [toestaan dat apps](customize-controlled-folders.md#allow-specific-apps-to-make-changes-to-controlled-folders) hen toegang geven tot de beveiligde mappen.</span><span class="sxs-lookup"><span data-stu-id="208b3-139">You can also [allow apps](customize-controlled-folders.md#allow-specific-apps-to-make-changes-to-controlled-folders) to give them access to the protected folders.</span></span>

<span data-ttu-id="208b3-140">U kunt de [auditmodus gebruiken om](audit-windows-defender.md) te evalueren hoe gecontroleerde maptoegang van invloed is op uw organisatie als deze is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="208b3-140">You can use [audit mode](audit-windows-defender.md) to evaluate how controlled folder access would impact your organization if it were enabled.</span></span> <span data-ttu-id="208b3-141">U kunt ook naar de website van Windows Defender Test ground [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) om te bevestigen dat de functie werkt en te zien hoe deze werkt.</span><span class="sxs-lookup"><span data-stu-id="208b3-141">You can also visit the Windows Defender Test ground website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the feature is working and see how it works.</span></span>

<span data-ttu-id="208b3-142">Gecontroleerde maptoegang wordt ondersteund in de volgende versies van Windows:</span><span class="sxs-lookup"><span data-stu-id="208b3-142">Controlled folder access is supported on the following versions of Windows:</span></span>
- <span data-ttu-id="208b3-143">[Windows 10, versie 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) en hoger</span><span class="sxs-lookup"><span data-stu-id="208b3-143">[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) and later</span></span>
- [<span data-ttu-id="208b3-144">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="208b3-144">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

## <a name="windows-system-folders-are-protected-by-default"></a><span data-ttu-id="208b3-145">Windows-systeemmappen zijn standaard beveiligd</span><span class="sxs-lookup"><span data-stu-id="208b3-145">Windows system folders are protected by default</span></span>

<span data-ttu-id="208b3-146">Windows-systeemmappen zijn standaard beveiligd, samen met verschillende andere mappen:</span><span class="sxs-lookup"><span data-stu-id="208b3-146">Windows system folders are protected by default, along with several other folders:</span></span> 

- `c:\Users\<username>\Documents`
- `c:\Users\Public\Documents`
- `c:\Users\<username>\Pictures`
- `c:\Users\Public\Pictures`
- `c:\Users\Public\Videos`
- `c:\Users\<username>\Videos`
- `c:\Users\<username>\Music`
- `c:\Users\Public\Music`
- `c:\Users\<username>\Favorites`

> [!NOTE]
> <span data-ttu-id="208b3-147">U kunt extra mappen als beveiligd configureren, maar u kunt de windows-systeemmappen die standaard zijn beveiligd niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="208b3-147">You can configure additional folders as protected, but you cannot remove the Windows system folders that are protected by default.</span></span>

## <a name="requirements-for-controlled-folder-access"></a><span data-ttu-id="208b3-148">Vereisten voor gecontroleerde maptoegang</span><span class="sxs-lookup"><span data-stu-id="208b3-148">Requirements for controlled folder access</span></span>

<span data-ttu-id="208b3-149">Voor gecontroleerde maptoegang is [het inschakelen van Realtime beveiliging](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)van Microsoft Defender Antivirus vereist.</span><span class="sxs-lookup"><span data-stu-id="208b3-149">Controlled folder access requires enabling [Microsoft Defender Antivirus real-time protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus).</span></span>

## <a name="review-controlled-folder-access-events-in-the-microsoft-defender-security-center"></a><span data-ttu-id="208b3-150">Gecontroleerde toegangsgebeurtenissen voor mappen bekijken in het Microsoft Defender-beveiligingscentrum</span><span class="sxs-lookup"><span data-stu-id="208b3-150">Review controlled folder access events in the Microsoft Defender Security Center</span></span>

<span data-ttu-id="208b3-151">Defender for Endpoint biedt gedetailleerde rapportage over gebeurtenissen en blokken als onderdeel van de [scenario's voor waarschuwingsonderzoek.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="208b3-151">Defender for Endpoint provides detailed reporting into events and blocks as part of its [alert investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="208b3-152">U kunt Microsoft Defender opvragen voor eindpuntgegevens met behulp van [Geavanceerd zoeken.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/advanced-hunting-windows-defender-advanced-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="208b3-152">You can query Microsoft Defender for Endpoint data by using [Advanced hunting](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/advanced-hunting-windows-defender-advanced-threat-protection).</span></span> <span data-ttu-id="208b3-153">Als u de [auditmodus gebruikt,](audit-windows-defender.md)kunt u geavanceerd zoeken gebruiken om te zien hoe de instellingen voor gecontroleerde maptoegang van invloed zijn op uw omgeving als deze zijn ingeschakeld. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="208b3-153">If you're using [audit mode](audit-windows-defender.md), you can use [advanced hunting](advanced-hunting-overview.md) to see how controlled folder access settings would affect your environment if they were enabled.</span></span>

<span data-ttu-id="208b3-154">Voorbeeldquery:</span><span class="sxs-lookup"><span data-stu-id="208b3-154">Example query:</span></span>

```PowerShell
DeviceEvents
| where ActionType in ('ControlledFolderAccessViolationAudited','ControlledFolderAccessViolationBlocked')
```

## <a name="review-controlled-folder-access-events-in-windows-event-viewer"></a><span data-ttu-id="208b3-155">Gecontroleerde maptoegangsgebeurtenissen bekijken in Windows Event Viewer</span><span class="sxs-lookup"><span data-stu-id="208b3-155">Review controlled folder access events in Windows Event Viewer</span></span>

<span data-ttu-id="208b3-156">U kunt het Windows-gebeurtenislogboek bekijken om gebeurtenissen te bekijken die worden gemaakt wanneer gecontroleerde maptoegangsblokken (of audits) van een app worden gemaakt:</span><span class="sxs-lookup"><span data-stu-id="208b3-156">You can review the Windows event log to see events that are created when controlled folder access blocks (or audits) an app:</span></span>

1. <span data-ttu-id="208b3-157">Download het [evaluatiepakket en](https://aka.ms/mp7z2w) haal het *bestand* cfa-events.xmlnaar een gemakkelijk toegankelijke locatie op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="208b3-157">Download the [Evaluation Package](https://aka.ms/mp7z2w) and extract the file *cfa-events.xml* to an easily accessible location on the device.</span></span>
2. <span data-ttu-id="208b3-158">Typ **Gebeurtenisviewer** in het menu Start om de Windows Event Viewer te openen.</span><span class="sxs-lookup"><span data-stu-id="208b3-158">Type **Event viewer** in the Start menu to open the Windows Event Viewer.</span></span>
3. <span data-ttu-id="208b3-159">Selecteer in het linkervenster onder **Acties** de optie **Aangepaste weergave importeren...**.</span><span class="sxs-lookup"><span data-stu-id="208b3-159">On the left panel, under **Actions**, select **Import custom view...**.</span></span>
4. <span data-ttu-id="208b3-160">Ga naar de plaats waar u *cfa-events.xml* en selecteer deze.</span><span class="sxs-lookup"><span data-stu-id="208b3-160">Navigate to where you extracted *cfa-events.xml* and select it.</span></span> <span data-ttu-id="208b3-161">U kunt ook [de XML rechtstreeks kopiëren.](event-views.md)</span><span class="sxs-lookup"><span data-stu-id="208b3-161">Alternatively, [copy the XML directly](event-views.md).</span></span>
5. <span data-ttu-id="208b3-162">Kies **OK**.</span><span class="sxs-lookup"><span data-stu-id="208b3-162">Select **OK**.</span></span>

<span data-ttu-id="208b3-163">In de volgende tabel ziet u gebeurtenissen met betrekking tot gecontroleerde maptoegang:</span><span class="sxs-lookup"><span data-stu-id="208b3-163">The following table shows events related to controlled folder access:</span></span>

|<span data-ttu-id="208b3-164">Gebeurtenis-id</span><span class="sxs-lookup"><span data-stu-id="208b3-164">Event ID</span></span> | <span data-ttu-id="208b3-165">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="208b3-165">Description</span></span> |
|:---|:---|
|<span data-ttu-id="208b3-166">5007</span><span class="sxs-lookup"><span data-stu-id="208b3-166">5007</span></span> | <span data-ttu-id="208b3-167">Gebeurtenis wanneer instellingen worden gewijzigd</span><span class="sxs-lookup"><span data-stu-id="208b3-167">Event when settings are changed</span></span> |
|<span data-ttu-id="208b3-168">1124</span><span class="sxs-lookup"><span data-stu-id="208b3-168">1124</span></span> | <span data-ttu-id="208b3-169">Gecontroleerde gecontroleerde maptoegangsgebeurtenis</span><span class="sxs-lookup"><span data-stu-id="208b3-169">Audited controlled folder access event</span></span> | 
|<span data-ttu-id="208b3-170">1123</span><span class="sxs-lookup"><span data-stu-id="208b3-170">1123</span></span> | <span data-ttu-id="208b3-171">Gebeurtenis Geblokkeerde gecontroleerde maptoegang</span><span class="sxs-lookup"><span data-stu-id="208b3-171">Blocked controlled folder access event</span></span> |

## <a name="view-or-change-the-list-of-protected-folders"></a><span data-ttu-id="208b3-172">De lijst met beveiligde mappen weergeven of wijzigen</span><span class="sxs-lookup"><span data-stu-id="208b3-172">View or change the list of protected folders</span></span>

<span data-ttu-id="208b3-173">U kunt de Windows Security-app gebruiken om de lijst met mappen weer te geven die zijn beveiligd met beheerde maptoegang.</span><span class="sxs-lookup"><span data-stu-id="208b3-173">You can use the Windows Security app to view the list of folders that are protected by controlled folder access.</span></span> 

1. <span data-ttu-id="208b3-174">Open de Windows Security-app op uw Windows 10-apparaat.</span><span class="sxs-lookup"><span data-stu-id="208b3-174">On your Windows 10 device, open the Windows Security app.</span></span>
2. <span data-ttu-id="208b3-175">Selecteer **Virusbeveiliging & bedreiging**.</span><span class="sxs-lookup"><span data-stu-id="208b3-175">Select **Virus & threat protection**.</span></span>
3. <span data-ttu-id="208b3-176">Selecteer **onder Ransomware-beveiliging** de optie **Ransomware-beveiliging beheren.**</span><span class="sxs-lookup"><span data-stu-id="208b3-176">Under **Ransomware protection**, select **Manage ransomware protection**.</span></span>
4. <span data-ttu-id="208b3-177">Als beheerde maptoegang is uitgeschakeld, moet u deze in- en uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="208b3-177">If controlled folder access is turned off, you'll need to turn it on.</span></span> <span data-ttu-id="208b3-178">Selecteer **beveiligde mappen.**</span><span class="sxs-lookup"><span data-stu-id="208b3-178">Select **protected folders**.</span></span>
5. <span data-ttu-id="208b3-179">Ga op een van de volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="208b3-179">Do one of the following steps:</span></span>
   - <span data-ttu-id="208b3-180">Als u een map wilt toevoegen, **selecteert u + Een beveiligde map toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="208b3-180">To add a folder, select **+ Add a protected folder**.</span></span>
   - <span data-ttu-id="208b3-181">Als u een map wilt verwijderen, selecteert u deze en selecteert u **Vervolgens Verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="208b3-181">To remove a folder, select it, and then select **Remove**.</span></span> 

> [!NOTE]
> <span data-ttu-id="208b3-182">[Windows-systeemmappen](#windows-system-folders-are-protected-by-default) zijn standaard beveiligd en u kunt ze niet uit de lijst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="208b3-182">[Windows system folders](#windows-system-folders-are-protected-by-default) are protected by default, and you cannot remove them from the list.</span></span>

## <a name="see-also"></a><span data-ttu-id="208b3-183">Zie ook</span><span class="sxs-lookup"><span data-stu-id="208b3-183">See also</span></span>

- [<span data-ttu-id="208b3-184">Beheerde maptoegang evalueren</span><span class="sxs-lookup"><span data-stu-id="208b3-184">Evaluate controlled folder access</span></span>](evaluate-controlled-folder-access.md)
- [<span data-ttu-id="208b3-185">Beheerde maptoegang aanpassen</span><span class="sxs-lookup"><span data-stu-id="208b3-185">Customize controlled folder access</span></span>](customize-controlled-folders.md)
- [<span data-ttu-id="208b3-186">Meer mappen beveiligen</span><span class="sxs-lookup"><span data-stu-id="208b3-186">Protect more folders</span></span>](customize-controlled-folders.md#protect-additional-folders)
