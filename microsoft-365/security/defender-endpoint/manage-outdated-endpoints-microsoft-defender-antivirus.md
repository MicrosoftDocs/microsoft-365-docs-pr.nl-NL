---
title: Microsoft Defender AV-beveiligingsupdates toepassen op verouderd eindpunten
description: Bepaal wanneer en hoe updates moeten worden toegepast voor eindpunten die al een tijdje niet zijn bijgewerkt.
keywords: updates, beveiliging, verouderd, verouderd, oud, catch-up
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 3f56c18b66a27adfb1384f5c3f5e6c06034247d4
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690432"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-scans-for-endpoints-that-are-out-of-date"></a><span data-ttu-id="8a1d5-104">Microsoft Defender Antivirus-updates en -scans beheren voor eindpunten die verouderd zijn</span><span class="sxs-lookup"><span data-stu-id="8a1d5-104">Manage Microsoft Defender Antivirus updates and scans for endpoints that are out of date</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="8a1d5-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="8a1d5-105">**Applies to:**</span></span>

- [<span data-ttu-id="8a1d5-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="8a1d5-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="8a1d5-107">Met Microsoft Defender Antivirus kunt u bepalen hoe lang een eindpunt een update kan voorkomen of hoeveel scans het kan missen voordat het moet worden bijgewerkt en gescand.</span><span class="sxs-lookup"><span data-stu-id="8a1d5-107">Microsoft Defender Antivirus lets you define how long an endpoint can avoid an update or how many scans it can miss before it is required to update and scan itself.</span></span> <span data-ttu-id="8a1d5-108">Dit is vooral handig in omgevingen waarin apparaten niet vaak zijn verbonden met een bedrijfs- of extern netwerk of apparaten die niet dagelijks worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="8a1d5-108">This is especially useful in environments where devices are not often connected to a corporate or external network, or devices that are not used on a daily basis.</span></span>

<span data-ttu-id="8a1d5-109">Een werknemer die bijvoorbeeld een bepaalde pc gebruikt, heeft drie dagen pauze en kan zich in die periode niet aanmelden bij zijn of haar pc.</span><span class="sxs-lookup"><span data-stu-id="8a1d5-109">For example, an employee that uses a particular PC is on break for three days and does not log on to their PC during that time.</span></span>

<span data-ttu-id="8a1d5-110">Wanneer de gebruiker weer aan het werk gaat en zich aanmeldt bij zijn of haar pc, controleert en downloadt Microsoft Defender Antivirus onmiddellijk de meest recente beveiligingsupdates en wordt een scan uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="8a1d5-110">When the user returns to work and logs on to their PC, Microsoft Defender Antivirus will immediately check and download the latest protection updates, and run a scan.</span></span>

## <a name="set-up-catch-up-protection-updates-for-endpoints-that-havent-updated-for-a-while"></a><span data-ttu-id="8a1d5-111">Inhaalbeveiligingsupdates instellen voor eindpunten die al een tijdje niet zijn bijgewerkt</span><span class="sxs-lookup"><span data-stu-id="8a1d5-111">Set up catch-up protection updates for endpoints that haven't updated for a while</span></span>

<span data-ttu-id="8a1d5-112">Als Microsoft Defender Antivirus beveiligingsupdates voor een bepaalde periode niet heeft gedownload, kunt u deze instellen op het automatisch controleren en downloaden van de nieuwste update bij de volgende keer dat u zich aanmeldt.</span><span class="sxs-lookup"><span data-stu-id="8a1d5-112">If Microsoft Defender Antivirus did not download protection updates for a specified period, you can set it up to automatically check and download the latest update at the next log on.</span></span> <span data-ttu-id="8a1d5-113">Dit is handig als u automatische updatedownloads bij het opstarten globaal [hebt uitgeschakeld.](manage-event-based-updates-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="8a1d5-113">This is useful if you have [globally disabled automatic update downloads on startup](manage-event-based-updates-microsoft-defender-antivirus.md).</span></span>

### <a name="use-configuration-manager-to-configure-catch-up-protection-updates"></a><span data-ttu-id="8a1d5-114">Configuration Manager gebruiken om inhaalbeveiligingsupdates te configureren</span><span class="sxs-lookup"><span data-stu-id="8a1d5-114">Use Configuration Manager to configure catch-up protection updates</span></span>

1.  <span data-ttu-id="8a1d5-115">Open op uw Microsoft Endpoint Manager-console het antimalwarebeleid dat u wilt wijzigen (klik op Activa en naleving **in** het navigatiedeelvenster aan de linkerkant en vouw de structuur vervolgens uit naar Het  >    >  **antimalwarebeleid voor endpointbeveiliging** van overzicht )</span><span class="sxs-lookup"><span data-stu-id="8a1d5-115">On your Microsoft Endpoint Manager console, open the antimalware policy you want to change (click **Assets and Compliance** in the navigation pane on the left, then expand the tree to **Overview** > **Endpoint Protection** > **Antimalware Policies**)</span></span>

2.  <span data-ttu-id="8a1d5-116">Ga naar de **sectie Beveiligingsinformatie-updates** en configureer de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="8a1d5-116">Go to the **Security intelligence updates** section and configure the following settings:</span></span>

    1. <span data-ttu-id="8a1d5-117">Stel **Een beveiligingsintelligentie-update in als de clientcomputer offline is voor** meer dan twee opeenvolgende geplande updates voor **Ja.**</span><span class="sxs-lookup"><span data-stu-id="8a1d5-117">Set **Force a security intelligence update if the client computer is offline for more than two consecutive scheduled updates** to **Yes**.</span></span>
    2. <span data-ttu-id="8a1d5-118">Geef voor  **If Configuration Manager** als bron voor beveiligingsinformatieupdates... de uren op waarvoor de beveiligingsupdates die door Configuration Manager worden geleverd, als verouderd moeten worden beschouwd.</span><span class="sxs-lookup"><span data-stu-id="8a1d5-118">For the  **If Configuration Manager is used as a source for security intelligence updates...**, specify the hours before which the protection updates delivered by Configuration Manager should be considered out-of-date.</span></span> <span data-ttu-id="8a1d5-119">Hierdoor wordt de volgende updatelocatie gebruikt op basis van de gedefinieerde [fallbackbronorder.](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)</span><span class="sxs-lookup"><span data-stu-id="8a1d5-119">This will cause the next update location to be used, based on the defined [fallback source order](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order).</span></span>

3. <span data-ttu-id="8a1d5-120">Klik op **OK**.</span><span class="sxs-lookup"><span data-stu-id="8a1d5-120">Click **OK**.</span></span>

4.  <span data-ttu-id="8a1d5-121">[Implementeer het bijgewerkte beleid zoals gewoonlijk.](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)</span><span class="sxs-lookup"><span data-stu-id="8a1d5-121">[Deploy the updated policy as usual](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).</span></span>

### <a name="use-group-policy-to-enable-and-configure-the-catch-up-update-feature"></a><span data-ttu-id="8a1d5-122">Groepsbeleid gebruiken om de functie voor het bijwerken van bijvangst in te stellen en te configureren</span><span class="sxs-lookup"><span data-stu-id="8a1d5-122">Use Group Policy to enable and configure the catch-up update feature</span></span>

1. <span data-ttu-id="8a1d5-123">Open op de computer groepsbeleidsbeheer de console Groepsbeleidsbeheer, [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik op **Bewerken.**</span><span class="sxs-lookup"><span data-stu-id="8a1d5-123">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="8a1d5-124">Ga in **de Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie.**</span><span class="sxs-lookup"><span data-stu-id="8a1d5-124">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="8a1d5-125">Klik **op Beleid** en vervolgens op **Beheersjablonen.**</span><span class="sxs-lookup"><span data-stu-id="8a1d5-125">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="8a1d5-126">Vouw de structuur uit **naar Windows-onderdelen > Microsoft Defender Antivirus > Signature Updates**.</span><span class="sxs-lookup"><span data-stu-id="8a1d5-126">Expand the tree to **Windows components > Microsoft Defender Antivirus > Signature Updates**.</span></span>

5. <span data-ttu-id="8a1d5-127">Dubbelklik op **de instelling Het aantal** dagen definiëren waarna een inhaalupdate voor beveiligingsinformatie vereist is en stel de optie in op **Ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="8a1d5-127">Double-click the **Define the number of days after which a catch-up security intelligence update is required** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="8a1d5-128">Voer het aantal dagen in waarop u wilt dat Microsoft Defender AV de meest recente beveiligingsupdate controleert en downloadt.</span><span class="sxs-lookup"><span data-stu-id="8a1d5-128">Enter the number of days after which you want Microsoft Defender AV to check for and download the latest protection update.</span></span>

6. <span data-ttu-id="8a1d5-129">Klik op **OK**.</span><span class="sxs-lookup"><span data-stu-id="8a1d5-129">Click **OK**.</span></span>

### <a name="use-powershell-cmdlets-to-configure-catch-up-protection-updates"></a><span data-ttu-id="8a1d5-130">PowerShell-cmdlets gebruiken om inhaalbeveiligingsupdates te configureren</span><span class="sxs-lookup"><span data-stu-id="8a1d5-130">Use PowerShell cmdlets to configure catch-up protection updates</span></span>

<span data-ttu-id="8a1d5-131">Gebruik de volgende cmdlets:</span><span class="sxs-lookup"><span data-stu-id="8a1d5-131">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -SignatureUpdateCatchupInterval
```

<span data-ttu-id="8a1d5-132">Zie [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md)  gebruiken om Microsoft Defender Antivirus- en [Defender-cmdlets](/powershell/module/defender/) te configureren en uit te voeren voor meer informatie over het gebruik van PowerShell met Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="8a1d5-132">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md)  and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-configure-catch-up-protection-updates"></a><span data-ttu-id="8a1d5-133">Windows Management Instruction (WMI) gebruiken om inhaalbeveiligingsupdates te configureren</span><span class="sxs-lookup"><span data-stu-id="8a1d5-133">Use Windows Management Instruction (WMI) to configure catch-up protection updates</span></span>

<span data-ttu-id="8a1d5-134">Gebruik de [ **methode Set** of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class voor de volgende eigenschappen:</span><span class="sxs-lookup"><span data-stu-id="8a1d5-134">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
SignatureUpdateCatchupInterval
```

<span data-ttu-id="8a1d5-135">Zie het volgende voor meer informatie en toegestane parameters:</span><span class="sxs-lookup"><span data-stu-id="8a1d5-135">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="8a1d5-136">Windows Defender WMIv2-API's</span><span class="sxs-lookup"><span data-stu-id="8a1d5-136">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="set-the-number-of-days-before-protection-is-reported-as-out-of-date"></a><span data-ttu-id="8a1d5-137">Het aantal dagen instellen voordat de beveiliging als verouderd wordt gerapporteerd</span><span class="sxs-lookup"><span data-stu-id="8a1d5-137">Set the number of days before protection is reported as out-of-date</span></span>

<span data-ttu-id="8a1d5-138">U kunt ook het aantal dagen opgeven waarop Microsoft Defender Antivirusbeveiliging wordt beschouwd als oud of verouderd.</span><span class="sxs-lookup"><span data-stu-id="8a1d5-138">You can also specify the number of days after which Microsoft Defender Antivirus protection is considered old or out-of-date.</span></span> <span data-ttu-id="8a1d5-139">Na het opgegeven aantal dagen meldt de client zich als verouderd en wordt er een fout weergegeven aan de gebruiker van de pc.</span><span class="sxs-lookup"><span data-stu-id="8a1d5-139">After the specified number of days, the client will report itself as out-of-date, and show an error to the user of the PC.</span></span> <span data-ttu-id="8a1d5-140">Het kan er ook toe leiden dat Microsoft Defender Antivirus probeert een update te downloaden van andere bronnen (op basis van de gedefinieerde [fallbackbronorder),](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)bijvoorbeeld wanneer u MMPC als secundaire bron gebruikt nadat U WSUS of Microsoft Update als eerste bron hebt opgegeven.</span><span class="sxs-lookup"><span data-stu-id="8a1d5-140">It may also cause Microsoft Defender Antivirus to attempt to download an update from other sources (based on the defined [fallback source order](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)), such as when using MMPC as a secondary source after setting WSUS or Microsoft Update as the first source.</span></span>

### <a name="use-group-policy-to-specify-the-number-of-days-before-protection-is-considered-out-of-date"></a><span data-ttu-id="8a1d5-141">Groepsbeleid gebruiken om het aantal dagen op te geven voordat beveiliging als verouderd wordt beschouwd</span><span class="sxs-lookup"><span data-stu-id="8a1d5-141">Use Group Policy to specify the number of days before protection is considered out-of-date</span></span>

1.  <span data-ttu-id="8a1d5-142">Open op uw groepsbeleidsbeheercomputer de [console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))Groepsbeleidsbeheer, klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik op **Bewerken.**</span><span class="sxs-lookup"><span data-stu-id="8a1d5-142">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

3.  <span data-ttu-id="8a1d5-143">Ga in **de Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie.**</span><span class="sxs-lookup"><span data-stu-id="8a1d5-143">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

4.  <span data-ttu-id="8a1d5-144">Klik **op Beleid** en vervolgens op **Beheersjablonen.**</span><span class="sxs-lookup"><span data-stu-id="8a1d5-144">Click **Policies** then **Administrative templates**.</span></span>

5.  <span data-ttu-id="8a1d5-145">Vouw de structuur uit naar **Windows-onderdelen > Microsoft Defender Antivirus > Signature Updates** en configureer de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="8a1d5-145">Expand the tree to **Windows components > Microsoft Defender Antivirus > Signature Updates** and configure the following settings:</span></span>

    1.  <span data-ttu-id="8a1d5-146">Dubbelklik op **Het aantal dagen definiëren voordat spywaredefinities** als verouderd worden beschouwd en stel de optie in op **Ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="8a1d5-146">Double-click **Define the number of days before spyware definitions are considered out of date** and set the option to **Enabled**.</span></span> <span data-ttu-id="8a1d5-147">Voer het aantal dagen in waarvoor u wilt dat Microsoft Defender AV spyware beveiligingsinformatie als verouderd beschouwt.</span><span class="sxs-lookup"><span data-stu-id="8a1d5-147">Enter the number of days after which you want Microsoft Defender AV to consider spyware Security intelligence to be out-of-date.</span></span>

    2. <span data-ttu-id="8a1d5-148">Klik op **OK**.</span><span class="sxs-lookup"><span data-stu-id="8a1d5-148">Click **OK**.</span></span>

    3.  <span data-ttu-id="8a1d5-149">Dubbelklik op **Het aantal dagen definiëren voordat virusdefinities** als verouderd worden beschouwd en stel de optie in op **Ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="8a1d5-149">Double-click **Define the number of days before virus definitions are considered out of date** and set the option to **Enabled**.</span></span> <span data-ttu-id="8a1d5-150">Voer het aantal dagen in waarvan u wilt dat Microsoft Defender AV virusbeveiligingsinformatie verouderd acht.</span><span class="sxs-lookup"><span data-stu-id="8a1d5-150">Enter the number of days after which you want Microsoft Defender AV to consider virus Security intelligence to be out-of-date.</span></span>

    4. <span data-ttu-id="8a1d5-151">Klik op **OK**.</span><span class="sxs-lookup"><span data-stu-id="8a1d5-151">Click **OK**.</span></span>


## <a name="set-up-catch-up-scans-for-endpoints-that-have-not-been-scanned-for-a-while"></a><span data-ttu-id="8a1d5-152">Inhaalscans instellen voor eindpunten die al een tijdje niet zijn gescand</span><span class="sxs-lookup"><span data-stu-id="8a1d5-152">Set up catch-up scans for endpoints that have not been scanned for a while</span></span>

<span data-ttu-id="8a1d5-153">U kunt het aantal opeenvolgende geplande scans instellen dat kan worden gemist voordat Microsoft Defender Antivirus een scan forceerd.</span><span class="sxs-lookup"><span data-stu-id="8a1d5-153">You can set the number of consecutive scheduled scans that can be missed before Microsoft Defender Antivirus will force a scan.</span></span>

<span data-ttu-id="8a1d5-154">Het proces voor het inschakelen van deze functie is:</span><span class="sxs-lookup"><span data-stu-id="8a1d5-154">The process for enabling this feature is:</span></span>

1. <span data-ttu-id="8a1d5-155">Ten minste één geplande scan instellen (zie het [onderwerp Scans plannen).](scheduled-catch-up-scans-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="8a1d5-155">Set up at least one scheduled scan (see the [Schedule scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md) topic).</span></span>
2. <span data-ttu-id="8a1d5-156">Schakel de functie voor inhaalscans in.</span><span class="sxs-lookup"><span data-stu-id="8a1d5-156">Enable the catch-up scan feature.</span></span>
3. <span data-ttu-id="8a1d5-157">Definieer het aantal scans dat kan worden overgeslagen voordat een inhaalscan wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="8a1d5-157">Define the number of scans that can be skipped before a catch-up scan occurs.</span></span>

<span data-ttu-id="8a1d5-158">Deze functie kan worden ingeschakeld voor zowel volledige als snelle scans.</span><span class="sxs-lookup"><span data-stu-id="8a1d5-158">This feature can be enabled for both full and quick scans.</span></span>

### <a name="use-group-policy-to-enable-and-configure-the-catch-up-scan-feature"></a><span data-ttu-id="8a1d5-159">Groepsbeleid gebruiken om de functie voor het inhalen van de scan in te stellen en te configureren</span><span class="sxs-lookup"><span data-stu-id="8a1d5-159">Use Group Policy to enable and configure the catch-up scan feature</span></span>

1.  <span data-ttu-id="8a1d5-160">Zorg ervoor dat u ten minste één geplande scan hebt ingesteld.</span><span class="sxs-lookup"><span data-stu-id="8a1d5-160">Ensure you have set up at least one scheduled scan.</span></span>

2.  <span data-ttu-id="8a1d5-161">Open op uw groepsbeleidsbeheercomputer de [console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))Groepsbeleidsbeheer, klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik op **Bewerken.**</span><span class="sxs-lookup"><span data-stu-id="8a1d5-161">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

3.  <span data-ttu-id="8a1d5-162">Ga in **de Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie.**</span><span class="sxs-lookup"><span data-stu-id="8a1d5-162">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

4.  <span data-ttu-id="8a1d5-163">Klik **op Beleid** en vervolgens op **Beheersjablonen.**</span><span class="sxs-lookup"><span data-stu-id="8a1d5-163">Click **Policies** then **Administrative templates**.</span></span>

5.  <span data-ttu-id="8a1d5-164">Vouw de structuur uit **naar Windows-onderdelen > Microsoft Defender Antivirus > De** volgende instellingen scannen en configureren:</span><span class="sxs-lookup"><span data-stu-id="8a1d5-164">Expand the tree to **Windows components > Microsoft Defender Antivirus > Scan** and configure the following settings:</span></span>

    1.  <span data-ttu-id="8a1d5-165">Als u geplande snelle scans hebt ingesteld,  dubbelklikt u op de instelling Snelscan inhalen inschakelen en stelt u de optie **in op Ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="8a1d5-165">If you have set up scheduled quick scans, double-click the **Turn on catch-up quick scan** setting and set the option to **Enabled**.</span></span> 
    2. <span data-ttu-id="8a1d5-166">Als u geplande volledige scans hebt ingesteld,  dubbelklikt u op de instelling Volledige inhaaloptie inschakelen en stelt u de optie **in op Ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="8a1d5-166">If you have set up scheduled full scans, double-click the **Turn on catch-up full scan** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="8a1d5-167">Klik op **OK**.</span><span class="sxs-lookup"><span data-stu-id="8a1d5-167">Click **OK**.</span></span>
    3. <span data-ttu-id="8a1d5-168">Dubbelklik op het aantal dagen definiëren waarna een **inhaalscan wordt** geforceerd en stel de optie in op **Ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="8a1d5-168">Double-click the **Define the number of days after which a catch-up scan is forced** setting and set the option to **Enabled**.</span></span> 
    4. <span data-ttu-id="8a1d5-169">Voer het aantal scans in dat kan worden gemist voordat een scan automatisch wordt uitgevoerd wanneer de gebruiker zich volgende keer aanmeldt bij de pc.</span><span class="sxs-lookup"><span data-stu-id="8a1d5-169">Enter the number of scans that can be missed before a scan will be automatically run when the user next logs on to the PC.</span></span> <span data-ttu-id="8a1d5-170">Het type scan dat wordt uitgevoerd, wordt bepaald door het scantype Opgeven dat moet worden gebruikt voor een **geplande scan** (zie het onderwerp [Planningsscans).](scheduled-catch-up-scans-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="8a1d5-170">The type of scan that is run is determined by the **Specify the scan type to use for a scheduled scan** (see the [Schedule scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md) topic).</span></span> <span data-ttu-id="8a1d5-171">Klik op **OK**.</span><span class="sxs-lookup"><span data-stu-id="8a1d5-171">Click **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="8a1d5-172">De instellingstitel Groepsbeleid verwijst naar het aantal dagen.</span><span class="sxs-lookup"><span data-stu-id="8a1d5-172">The Group Policy setting title refers to the number of days.</span></span> <span data-ttu-id="8a1d5-173">De instelling wordt echter toegepast op het aantal scans (niet dagen) voordat de inhaalscan wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="8a1d5-173">The setting, however, is applied to the number of scans (not days) before the catch-up scan will be run.</span></span>

### <a name="use-powershell-cmdlets-to-configure-catch-up-scans"></a><span data-ttu-id="8a1d5-174">PowerShell-cmdlets gebruiken om inhaalscans te configureren</span><span class="sxs-lookup"><span data-stu-id="8a1d5-174">Use PowerShell cmdlets to configure catch-up scans</span></span>

<span data-ttu-id="8a1d5-175">Gebruik de volgende cmdlets:</span><span class="sxs-lookup"><span data-stu-id="8a1d5-175">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -DisableCatchupFullScan
Set-MpPreference -DisableCatchupQuickScan

```

<span data-ttu-id="8a1d5-176">Zie [PowerShell-cmdlets gebruiken](use-powershell-cmdlets-microsoft-defender-antivirus.md)  om Microsoft Defender Antivirus- en [Defender-cmdlets](/powershell/module/defender/) te beheren voor meer informatie over het gebruik van PowerShell met Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="8a1d5-176">See [Use PowerShell cmdlets to manage Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md)  and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-configure-catch-up-scans"></a><span data-ttu-id="8a1d5-177">Windows Management Instruction (WMI) gebruiken om inhaalscans te configureren</span><span class="sxs-lookup"><span data-stu-id="8a1d5-177">Use Windows Management Instruction (WMI) to configure catch-up scans</span></span>

<span data-ttu-id="8a1d5-178">Gebruik de [ **methode Set** of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class voor de volgende eigenschappen:</span><span class="sxs-lookup"><span data-stu-id="8a1d5-178">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
DisableCatchupFullScan
DisableCatchupQuickScan
```

<span data-ttu-id="8a1d5-179">Zie het volgende voor meer informatie en toegestane parameters:</span><span class="sxs-lookup"><span data-stu-id="8a1d5-179">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="8a1d5-180">Windows Defender WMIv2-API's</span><span class="sxs-lookup"><span data-stu-id="8a1d5-180">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


### <a name="use-configuration-manager-to-configure-catch-up-scans"></a><span data-ttu-id="8a1d5-181">Configuratiebeheer gebruiken om inhaalscans te configureren</span><span class="sxs-lookup"><span data-stu-id="8a1d5-181">Use Configuration Manager to configure catch-up scans</span></span>

1.  <span data-ttu-id="8a1d5-182">Open op uw Microsoft Endpoint Manager-console het antimalwarebeleid dat u wilt wijzigen (klik op Activa en naleving **in** het navigatiedeelvenster aan de linkerkant en vouw de structuur vervolgens uit naar Het  >    >  **antimalwarebeleid voor endpointbeveiliging** van overzicht )</span><span class="sxs-lookup"><span data-stu-id="8a1d5-182">On your Microsoft Endpoint Manager console, open the antimalware policy you want to change (click **Assets and Compliance** in the navigation pane on the left, then expand the tree to **Overview** > **Endpoint Protection** > **Antimalware Policies**)</span></span>

2.  <span data-ttu-id="8a1d5-183">Ga naar de **sectie Geplande scans** en forceer een scan van het geselecteerde scantype als de **clientcomputer offline is...** naar **Ja.**</span><span class="sxs-lookup"><span data-stu-id="8a1d5-183">Go to the **Scheduled scans** section and **Force a scan of the selected scan type if client computer is offline...** to **Yes**.</span></span> 

3. <span data-ttu-id="8a1d5-184">Klik op **OK**.</span><span class="sxs-lookup"><span data-stu-id="8a1d5-184">Click **OK**.</span></span>

4.  <span data-ttu-id="8a1d5-185">[Implementeer het bijgewerkte beleid zoals gewoonlijk.](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)</span><span class="sxs-lookup"><span data-stu-id="8a1d5-185">[Deploy the updated policy as usual](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).</span></span>

## <a name="related-articles"></a><span data-ttu-id="8a1d5-186">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="8a1d5-186">Related articles</span></span>

- [<span data-ttu-id="8a1d5-187">Microsoft Defender Antivirus implementeren</span><span class="sxs-lookup"><span data-stu-id="8a1d5-187">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)
- [<span data-ttu-id="8a1d5-188">Microsoft Defender Antivirus-updates beheren en basislijnen toepassen</span><span class="sxs-lookup"><span data-stu-id="8a1d5-188">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="8a1d5-189">Beheren wanneer beveiligingsupdates moeten worden gedownload en toegepast</span><span class="sxs-lookup"><span data-stu-id="8a1d5-189">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md)
- [<span data-ttu-id="8a1d5-190">Geforceerd updates op basis van gebeurtenissen beheren</span><span class="sxs-lookup"><span data-stu-id="8a1d5-190">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md)
- [<span data-ttu-id="8a1d5-191">Updates voor mobiele apparaten en virtuele machines (VM's) beheren</span><span class="sxs-lookup"><span data-stu-id="8a1d5-191">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [<span data-ttu-id="8a1d5-192">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="8a1d5-192">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)