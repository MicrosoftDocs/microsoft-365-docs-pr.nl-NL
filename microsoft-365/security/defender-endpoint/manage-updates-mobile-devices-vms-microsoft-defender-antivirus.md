---
title: Definieer hoe mobiele apparaten worden bijgewerkt door Microsoft Defender Antivirus
description: Beheer hoe mobiele apparaten, zoals laptops, moeten worden bijgewerkt met beveiligingsupdates voor Microsoft Defender Antivirus.
keywords: updates, beveiliging, planningsupdates, batterij, mobiel apparaat, laptop, notitieblok, opt-in, microsoft-update, wsus, overschrijven
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 826e1456de2aadf4031a91e30925a1e771d44f70
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765585"
---
# <a name="manage-updates-for-mobile-devices-and-virtual-machines-vms"></a><span data-ttu-id="cce79-104">Updates beheren voor mobiele apparaten en virtuele machines (VM's)</span><span class="sxs-lookup"><span data-stu-id="cce79-104">Manage updates for mobile devices and virtual machines (VMs)</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="cce79-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="cce79-105">**Applies to:**</span></span>

- [<span data-ttu-id="cce79-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="cce79-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="cce79-107">Mobiele apparaten en VM's hebben mogelijk meer configuratie nodig om ervoor te zorgen dat de prestaties niet worden beïnvloed door updates.</span><span class="sxs-lookup"><span data-stu-id="cce79-107">Mobile devices and VMs may require more configuration to ensure performance is not impacted by updates.</span></span>

<span data-ttu-id="cce79-108">Er zijn twee instellingen die handig zijn voor deze apparaten:</span><span class="sxs-lookup"><span data-stu-id="cce79-108">There are two settings that are useful for these devices:</span></span>

- <span data-ttu-id="cce79-109">Kies voor Microsoft Update op mobiele computers zonder WSUS-verbinding</span><span class="sxs-lookup"><span data-stu-id="cce79-109">Opt in to Microsoft Update on mobile computers without a WSUS connection</span></span>
- <span data-ttu-id="cce79-110">Beveiligingsintelligentie-updates voorkomen wanneer de batterij wordt gebruikt</span><span class="sxs-lookup"><span data-stu-id="cce79-110">Prevent Security intelligence updates when running on battery power</span></span>

<span data-ttu-id="cce79-111">De volgende artikelen kunnen ook handig zijn in deze situaties:</span><span class="sxs-lookup"><span data-stu-id="cce79-111">The following articles may also be useful in these situations:</span></span>
- [<span data-ttu-id="cce79-112">Geplande scans en inhaalscans configureren</span><span class="sxs-lookup"><span data-stu-id="cce79-112">Configuring scheduled and catch-up scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="cce79-113">Updates beheren voor eindpunten die verouderd zijn</span><span class="sxs-lookup"><span data-stu-id="cce79-113">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [<span data-ttu-id="cce79-114">Implementatiehandleiding voor Microsoft Defender Antivirus in een VDI-omgeving (Virtual Desktop Infrastructure)</span><span class="sxs-lookup"><span data-stu-id="cce79-114">Deployment guide for Microsoft Defender Antivirus in a virtual desktop infrastructure (VDI) environment</span></span>](deployment-vdi-microsoft-defender-antivirus.md)

## <a name="opt-in-to-microsoft-update-on-mobile-computers-without-a-wsus-connection"></a><span data-ttu-id="cce79-115">Kies voor Microsoft Update op mobiele computers zonder WSUS-verbinding</span><span class="sxs-lookup"><span data-stu-id="cce79-115">Opt in to Microsoft Update on mobile computers without a WSUS connection</span></span>

<span data-ttu-id="cce79-116">U kunt Microsoft Update gebruiken om beveiligingsinformatie op mobiele apparaten met Microsoft Defender Antivirus up-to-date te houden wanneer ze niet zijn verbonden met het bedrijfsnetwerk of anders geen WSUS-verbinding hebben.</span><span class="sxs-lookup"><span data-stu-id="cce79-116">You can use Microsoft Update to keep Security intelligence on mobile devices running Microsoft Defender Antivirus up to date when they are not connected to the corporate network or don't otherwise have a WSUS connection.</span></span> 

<span data-ttu-id="cce79-117">Dit betekent dat beveiligingsupdates kunnen worden geleverd op apparaten (via Microsoft Update), zelfs als u WSUS hebt ingesteld om Microsoft Update te overschrijven.</span><span class="sxs-lookup"><span data-stu-id="cce79-117">This means that protection updates can be delivered to devices (via Microsoft Update) even if you have set WSUS to override Microsoft Update.</span></span>

<span data-ttu-id="cce79-118">U kunt op een van de volgende manieren kiezen voor Microsoft Update op het mobiele apparaat:</span><span class="sxs-lookup"><span data-stu-id="cce79-118">You can opt in to Microsoft Update on the mobile device in one of the following ways:</span></span>

- <span data-ttu-id="cce79-119">Wijzig de instelling met Groepsbeleid.</span><span class="sxs-lookup"><span data-stu-id="cce79-119">Change the setting with Group Policy.</span></span>
- <span data-ttu-id="cce79-120">Gebruik een VBScript om een script te maken en voer het vervolgens uit op elke computer in uw netwerk.</span><span class="sxs-lookup"><span data-stu-id="cce79-120">Use a VBScript to create a script, then run it on each computer in your network.</span></span>
- <span data-ttu-id="cce79-121">Kies handmatig op elke computer in uw netwerk via **het** menu Instellingen.</span><span class="sxs-lookup"><span data-stu-id="cce79-121">Manually opt in every computer on your network through the **Settings** menu.</span></span>

### <a name="use-group-policy-to-opt-in-to-microsoft-update"></a><span data-ttu-id="cce79-122">Groepsbeleid gebruiken om u aan te geven bij Microsoft Update</span><span class="sxs-lookup"><span data-stu-id="cce79-122">Use Group Policy to opt in to Microsoft Update</span></span>

1. <span data-ttu-id="cce79-123">Open op uw groepsbeleidsbeheercomputer de console Groepsbeleidsbeheer, [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en selecteer **Bewerken.**</span><span class="sxs-lookup"><span data-stu-id="cce79-123">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="cce79-124">Ga in **de Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie.**</span><span class="sxs-lookup"><span data-stu-id="cce79-124">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="cce79-125">Selecteer **Beleid en** **beheersjablonen.**</span><span class="sxs-lookup"><span data-stu-id="cce79-125">Select **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="cce79-126">Vouw de boom uit naar **Windows-onderdelen**  >  **Microsoft Defender Antivirus** Signature  >  **Updates**.</span><span class="sxs-lookup"><span data-stu-id="cce79-126">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Signature Updates**.</span></span>

5. <span data-ttu-id="cce79-127">Stel **Beveiligingsintelligentie-updates van Microsoft Update toestaan** in op **Ingeschakeld** en selecteer **OK.**</span><span class="sxs-lookup"><span data-stu-id="cce79-127">Set **Allow security intelligence updates from Microsoft Update** to **Enabled**, and then select  **OK**.</span></span>


### <a name="use-a-vbscript-to-opt-in-to-microsoft-update"></a><span data-ttu-id="cce79-128">Een VBScript gebruiken om u aan te geven bij Microsoft Update</span><span class="sxs-lookup"><span data-stu-id="cce79-128">Use a VBScript to opt in to Microsoft Update</span></span>

1. <span data-ttu-id="cce79-129">Gebruik de instructies in het [MSDN-artikel Opt-In to Microsoft Update](/windows/win32/wua_sdk/opt-in-to-microsoft-update) om de VBScript te maken.</span><span class="sxs-lookup"><span data-stu-id="cce79-129">Use the instructions in the MSDN article [Opt-In to Microsoft Update](/windows/win32/wua_sdk/opt-in-to-microsoft-update) to create the VBScript.</span></span>

2. <span data-ttu-id="cce79-130">Voer de VBScript uit die u op elke computer in uw netwerk hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="cce79-130">Run the VBScript you created on each computer in your network.</span></span>

### <a name="manually-opt-in-to-microsoft-update"></a><span data-ttu-id="cce79-131">Handmatig kiezen voor Microsoft Update</span><span class="sxs-lookup"><span data-stu-id="cce79-131">Manually opt in to Microsoft Update</span></span>

1. <span data-ttu-id="cce79-132">Open **Windows Update** in Update & **beveiligingsinstellingen** op de computer waarin u zich wilt opgeven.</span><span class="sxs-lookup"><span data-stu-id="cce79-132">Open **Windows Update** in **Update & security** settings on the computer you want to opt in.</span></span>

2. <span data-ttu-id="cce79-133">Selecteer **Geavanceerde** opties.</span><span class="sxs-lookup"><span data-stu-id="cce79-133">Select **Advanced** options.</span></span>

3. <span data-ttu-id="cce79-134">Schakel het selectievakje Voor mij updates voor andere **Microsoft-producten in** wanneer ik Windows bij werk.</span><span class="sxs-lookup"><span data-stu-id="cce79-134">Select the checkbox for **Give me updates for other Microsoft products when I update Windows**.</span></span>

## <a name="prevent-security-intelligence-updates-when-running-on-battery-power"></a><span data-ttu-id="cce79-135">Beveiligingsintelligentie-updates voorkomen wanneer de batterij wordt gebruikt</span><span class="sxs-lookup"><span data-stu-id="cce79-135">Prevent Security intelligence updates when running on battery power</span></span>

<span data-ttu-id="cce79-136">U kunt Microsoft Defender Antivirus zo configureren dat alleen beveiligingsupdates worden gedownload wanneer de pc is verbonden met een bekabelde stroombron.</span><span class="sxs-lookup"><span data-stu-id="cce79-136">You can configure Microsoft Defender Antivirus to only download protection updates when the PC is connected to a wired power source.</span></span> 

### <a name="use-group-policy-to-prevent-security-intelligence-updates-on-battery-power"></a><span data-ttu-id="cce79-137">Groepsbeleid gebruiken om beveiligingsintelligentie-updates voor accu's te voorkomen</span><span class="sxs-lookup"><span data-stu-id="cce79-137">Use Group Policy to prevent security intelligence updates on battery power</span></span>

1.  <span data-ttu-id="cce79-138">Open op uw groepsbeleidsbeheercomputer de console Groepsbeleidsbeheer, kies het groepsbeleidsobject dat u wilt configureren en open het voor bewerken. [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="cce79-138">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), choose the Group Policy Object you want to configure, and open it for editing.</span></span>

2.  <span data-ttu-id="cce79-139">Ga in **de Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie.**</span><span class="sxs-lookup"><span data-stu-id="cce79-139">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3.  <span data-ttu-id="cce79-140">Selecteer **Beleid en** **beheersjablonen.**</span><span class="sxs-lookup"><span data-stu-id="cce79-140">Select **Policies** then **Administrative templates**.</span></span>

4.  <span data-ttu-id="cce79-141">Vouw de structuur uit **naar Windows-onderdelen** Microsoft Defender Antivirus Signature Updates en stel beveiligingsintelligentie-updates toestaan wanneer u op de batterij werkt in  >    >  op **Uitgeschakeld.** </span><span class="sxs-lookup"><span data-stu-id="cce79-141">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Signature Updates**, and then set **Allow security intelligence updates when running on battery power** to **Disabled**.</span></span> <span data-ttu-id="cce79-142">Selecteer vervolgens **OK**.</span><span class="sxs-lookup"><span data-stu-id="cce79-142">Then select **OK**.</span></span> 

<span data-ttu-id="cce79-143">Met deze actie wordt voorkomen dat beveiligingsupdates worden gedownload wanneer de pc op de batterij staat.</span><span class="sxs-lookup"><span data-stu-id="cce79-143">This action prevents protection updates from downloading when the PC is on battery power.</span></span>

## <a name="related-articles"></a><span data-ttu-id="cce79-144">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="cce79-144">Related articles</span></span>

- [<span data-ttu-id="cce79-145">Microsoft Defender Antivirus-updates beheren en basislijnen toepassen</span><span class="sxs-lookup"><span data-stu-id="cce79-145">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="cce79-146">Microsoft Defender Antivirus bijwerken en beheren in Windows 10</span><span class="sxs-lookup"><span data-stu-id="cce79-146">Update and manage Microsoft Defender Antivirus in Windows 10</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)