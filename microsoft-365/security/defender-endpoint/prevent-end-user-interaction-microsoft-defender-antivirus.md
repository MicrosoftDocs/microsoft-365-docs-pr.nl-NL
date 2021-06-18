---
title: De interface Microsoft Defender Antivirus verbergen
description: U kunt de tegel virus- en bedreigingsbeveiliging verbergen in de Windows-beveiliging app.
keywords: ui lockdown, headless mode, hide app, hide settings, hide interface
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: ff0e134d38288b12cbc46dc3ca5f103fbf8c7ad9
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007662"
---
# <a name="prevent-users-from-seeing-or-interacting-with-the-microsoft-defender-antivirus-user-interface"></a><span data-ttu-id="1ba70-104">Voorkomen dat gebruikers de gebruikersinterface van de Microsoft Defender Antivirus zien of gebruiken</span><span class="sxs-lookup"><span data-stu-id="1ba70-104">Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="1ba70-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="1ba70-105">**Applies to:**</span></span>

- [<span data-ttu-id="1ba70-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="1ba70-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="1ba70-107">U kunt Groepsbeleid gebruiken om te voorkomen dat gebruikers op eindpunten de Microsoft Defender Antivirus zien.</span><span class="sxs-lookup"><span data-stu-id="1ba70-107">You can use Group Policy to prevent users on endpoints from seeing the Microsoft Defender Antivirus interface.</span></span> <span data-ttu-id="1ba70-108">U kunt ook voorkomen dat ze scans onderbreken.</span><span class="sxs-lookup"><span data-stu-id="1ba70-108">You can also prevent them from pausing scans.</span></span>

## <a name="hide-the-microsoft-defender-antivirus-interface"></a><span data-ttu-id="1ba70-109">De interface Microsoft Defender Antivirus verbergen</span><span class="sxs-lookup"><span data-stu-id="1ba70-109">Hide the Microsoft Defender Antivirus interface</span></span>

<span data-ttu-id="1ba70-110">In Windows 10, versie 1703, worden Microsoft Defender Antivirus-meldingen verborgen door de interface te verbergen en wordt voorkomen dat de tegel Virus & bedreigingsbeveiliging wordt weergegeven in de Windows-beveiliging-app.</span><span class="sxs-lookup"><span data-stu-id="1ba70-110">In Windows 10, versions 1703, hiding the interface will hide Microsoft Defender Antivirus notifications and prevent the Virus & threat protection tile from appearing in the Windows Security app.</span></span>

<span data-ttu-id="1ba70-111">Met de instelling ingesteld op **Ingeschakeld:**</span><span class="sxs-lookup"><span data-stu-id="1ba70-111">With the setting set to **Enabled**:</span></span>

:::image type="content" source="../../media/wdav-headless-mode-1703.png" alt-text="Windows-beveiliging zonder het schildpictogram en de sectie virus- en bedreigingsbeveiliging":::

<span data-ttu-id="1ba70-113">Met de instelling ingesteld op **Uitgeschakeld of** niet geconfigureerd:</span><span class="sxs-lookup"><span data-stu-id="1ba70-113">With the setting set to **Disabled** or not configured:</span></span>

:::image type="content" source="../../media/wdav-headless-mode-1703.png" alt-text="Schermafbeelding van Windows-beveiliging met schildpictogram en secties voor bedreigingsbeveiliging":::

>[!NOTE]
><span data-ttu-id="1ba70-115">Als u de interface verbergt, worden Microsoft Defender Antivirus meldingen ook niet weergegeven op het eindpunt.</span><span class="sxs-lookup"><span data-stu-id="1ba70-115">Hiding the interface will also prevent Microsoft Defender Antivirus notifications from appearing on the endpoint.</span></span> <span data-ttu-id="1ba70-116">Microsoft Defender voor eindpuntmeldingen wordt nog steeds weergegeven.</span><span class="sxs-lookup"><span data-stu-id="1ba70-116">Microsoft Defender for Endpoint notifications will still appear.</span></span> <span data-ttu-id="1ba70-117">U kunt de meldingen die op eindpunten worden weergegeven, ook [afzonderlijk configureren](configure-notifications-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="1ba70-117">You can also individually [configure the notifications that appear on endpoints](configure-notifications-microsoft-defender-antivirus.md)</span></span>

<span data-ttu-id="1ba70-118">In eerdere versies van Windows 10, verbergt de instelling de Windows Defender clientinterface.</span><span class="sxs-lookup"><span data-stu-id="1ba70-118">In earlier versions of Windows 10, the setting will hide the Windows Defender client interface.</span></span> <span data-ttu-id="1ba70-119">Als de gebruiker probeert deze te openen, ontvangt deze een waarschuwing met de melding 'Uw systeembeheerder heeft beperkte toegang tot deze app'.</span><span class="sxs-lookup"><span data-stu-id="1ba70-119">If the user attempts to open it, they will receive a warning that says, "Your system administrator has restricted access to this app."</span></span>

:::image type="content" source="../../media/wdav-headless-mode-1607.png" alt-text="Waarschuwingsbericht wanneer de headless-modus is ingeschakeld in Windows 10, versies eerder dan 1703":::

## <a name="use-group-policy-to-hide-the-microsoft-defender-av-interface-from-users"></a><span data-ttu-id="1ba70-121">Groepsbeleid gebruiken om de AV-interface van Microsoft Defender te verbergen voor gebruikers</span><span class="sxs-lookup"><span data-stu-id="1ba70-121">Use Group Policy to hide the Microsoft Defender AV interface from users</span></span>

1. <span data-ttu-id="1ba70-122">Open op uw groepsbeleidsbeheercomputer de [console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)Groepsbeleidsbeheer, klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik op **Bewerken.**</span><span class="sxs-lookup"><span data-stu-id="1ba70-122">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="1ba70-123">Ga met **de Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie.**</span><span class="sxs-lookup"><span data-stu-id="1ba70-123">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="1ba70-124">Klik **op Beheersjablonen.**</span><span class="sxs-lookup"><span data-stu-id="1ba70-124">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="1ba70-125">Vouw de structuur uit **Windows onderdelen > Microsoft Defender Antivirus > clientinterface.**</span><span class="sxs-lookup"><span data-stu-id="1ba70-125">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span>

5. <span data-ttu-id="1ba70-126">Dubbelklik op de instelling voor de modus Gebruikersinterface zonder hoofd **inschakelen** en stel de optie in op **Ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="1ba70-126">Double-click the **Enable headless UI mode** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="1ba70-127">Klik op **OK**.</span><span class="sxs-lookup"><span data-stu-id="1ba70-127">Click **OK**.</span></span> 

<span data-ttu-id="1ba70-128">Zie [Voorkomen dat gebruikers beleidsinstellingen](configure-local-policy-overrides-microsoft-defender-antivirus.md) lokaal wijzigen voor meer opties om te voorkomen dat gebruikers de beveiliging op hun pc wijzigen.</span><span class="sxs-lookup"><span data-stu-id="1ba70-128">See [Prevent users from locally modifying policy settings](configure-local-policy-overrides-microsoft-defender-antivirus.md) for more options on preventing users form modifying protection on their PCs.</span></span>

## <a name="prevent-users-from-pausing-a-scan"></a><span data-ttu-id="1ba70-129">Voorkomen dat gebruikers een scan onderbreken</span><span class="sxs-lookup"><span data-stu-id="1ba70-129">Prevent users from pausing a scan</span></span>

<span data-ttu-id="1ba70-130">U kunt voorkomen dat gebruikers scans onderbreken, wat handig kan zijn om ervoor te zorgen dat geplande of on-demand scans niet worden onderbroken door gebruikers.</span><span class="sxs-lookup"><span data-stu-id="1ba70-130">You can prevent users from pausing scans, which can be helpful to ensure scheduled or on-demand scans are not interrupted by users.</span></span>

> [!NOTE]
> <span data-ttu-id="1ba70-131">Deze instelling wordt niet ondersteund op Windows 10.</span><span class="sxs-lookup"><span data-stu-id="1ba70-131">This setting is not supported on Windows 10.</span></span>

### <a name="use-group-policy-to-prevent-users-from-pausing-a-scan"></a><span data-ttu-id="1ba70-132">Groepsbeleid gebruiken om te voorkomen dat gebruikers een scan onderbreken</span><span class="sxs-lookup"><span data-stu-id="1ba70-132">Use Group Policy to prevent users from pausing a scan</span></span>

1. <span data-ttu-id="1ba70-133">Open op uw groepsbeleidsbeheercomputer de [console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)Groepsbeleidsbeheer, klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik op **Bewerken.**</span><span class="sxs-lookup"><span data-stu-id="1ba70-133">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="1ba70-134">Ga met **de Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie.**</span><span class="sxs-lookup"><span data-stu-id="1ba70-134">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="1ba70-135">Klik **op Beheersjablonen.**</span><span class="sxs-lookup"><span data-stu-id="1ba70-135">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="1ba70-136">Vouw de boom uit Windows **onderdelen**  >  **Microsoft Defender Antivirus**  >  **Scannen.**</span><span class="sxs-lookup"><span data-stu-id="1ba70-136">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

5. <span data-ttu-id="1ba70-137">Dubbelklik op de **instelling Toestaan dat gebruikers de scan onderbreken** en stel de optie in op **Uitgeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="1ba70-137">Double-click the **Allow users to pause scan** setting and set the option to **Disabled**.</span></span> <span data-ttu-id="1ba70-138">Klik op **OK**.</span><span class="sxs-lookup"><span data-stu-id="1ba70-138">Click **OK**.</span></span> 

## <a name="related-articles"></a><span data-ttu-id="1ba70-139">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="1ba70-139">Related articles</span></span>

- [<span data-ttu-id="1ba70-140">De meldingen configureren die worden weergegeven op eindpunten</span><span class="sxs-lookup"><span data-stu-id="1ba70-140">Configure the notifications that appear on endpoints</span></span>](configure-notifications-microsoft-defender-antivirus.md)

- [<span data-ttu-id="1ba70-141">Interactie tussen eindgebruikers configureren met Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="1ba70-141">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md)

- [<span data-ttu-id="1ba70-142">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="1ba70-142">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)