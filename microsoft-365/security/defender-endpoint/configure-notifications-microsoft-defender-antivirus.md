---
title: Meldingen Microsoft Defender Antivirus configureren
description: Informatie over het configureren en aanpassen van zowel standaard- als Microsoft Defender Antivirus meldingen op eindpunten.
keywords: meldingen, defender, antivirus, eindpunt, beheer, beheerder
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.topic: article
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/16/2021
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: a7a838bb15cd011b750fbfa3d6df100ddf9f713c
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985406"
---
# <a name="configure-microsoft-defender-antivirus-notifications-that-appear-on-endpoints"></a><span data-ttu-id="40097-104">Meldingen Microsoft Defender Antivirus eindpunten configureren</span><span class="sxs-lookup"><span data-stu-id="40097-104">Configure Microsoft Defender Antivirus notifications that appear on endpoints</span></span>

<span data-ttu-id="40097-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="40097-105">**Applies to:**</span></span>

- [<span data-ttu-id="40097-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="40097-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="40097-107">In Windows 10 zijn toepassingsmeldingen over malwaredetectie en -herstel krachtiger, consistenter en beknopter.</span><span class="sxs-lookup"><span data-stu-id="40097-107">In Windows 10, application notifications about malware detection and remediation are more robust, consistent, and concise.</span></span> <span data-ttu-id="40097-108">Microsoft Defender Antivirus meldingen worden weergegeven op eindpunten wanneer scans worden voltooid en bedreigingen worden gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="40097-108">Microsoft Defender Antivirus notifications appear on endpoints when scans are completed and threats are detected.</span></span> <span data-ttu-id="40097-109">Meldingen volgen zowel geplande als handmatig geactiveerde scans.</span><span class="sxs-lookup"><span data-stu-id="40097-109">Notifications follow both scheduled and manually triggered scans.</span></span> <span data-ttu-id="40097-110">Deze meldingen worden ook weergegeven in het **systeemmeldingscentrum** en er wordt regelmatig een overzicht van scans en bedreigingsdetecties weergegeven.</span><span class="sxs-lookup"><span data-stu-id="40097-110">These notifications also appear in the **Notification Center**, and a summary of scans and threat detections appear at regular time intervals.</span></span>

<span data-ttu-id="40097-111">Als u deel uitmaakt van het beveiligingsteam van uw organisatie, kunt u configureren hoe meldingen worden weergegeven op eindpunten, zoals meldingen die vragen om een systeem opnieuw op te starten of die aangeven dat er een bedreiging is gedetecteerd en die zijn verwijderd.</span><span class="sxs-lookup"><span data-stu-id="40097-111">If you're part of your organization's security team, you can configure how notifications appear on endpoints, such as notifications that prompt for a system reboot or that indicate a threat has been detected and remediated.</span></span>

## <a name="configure-antivirus-notifications-using-group-policy-or-the-windows-security-app"></a><span data-ttu-id="40097-112">Antivirusmeldingen configureren met groepsbeleid of de Windows-beveiliging app</span><span class="sxs-lookup"><span data-stu-id="40097-112">Configure antivirus notifications using Group Policy or the Windows Security app</span></span>

<span data-ttu-id="40097-113">U kunt de weergave van extra meldingen, zoals recente samenvattingen voor bedreigingsdetectie, configureren in de Windows-beveiliging [app](microsoft-defender-security-center-antivirus.md) en met groepsbeleid.</span><span class="sxs-lookup"><span data-stu-id="40097-113">You can configure the display of additional notifications, such as recent threat detection summaries, in the [Windows Security app](microsoft-defender-security-center-antivirus.md) and with Group Policy.</span></span>

> [!NOTE]
> <span data-ttu-id="40097-114">In Windows 10 versie 1607 werd de functie **Enhanced notifications** genoemd en geconfigureerd **onder Windows Instellingen**  >  **Update &**  >  **beveiligingsinstellingen Windows Defender.**</span><span class="sxs-lookup"><span data-stu-id="40097-114">In Windows 10, version 1607 the feature was called **Enhanced notifications** and was configured under **Windows Settings** > **Update & security** > **Windows Defender**.</span></span> <span data-ttu-id="40097-115">In groepsbeleidsinstellingen voor alle versies van Windows 10 wordt de meldingsfunctie **Enhanced notifications genoemd.**</span><span class="sxs-lookup"><span data-stu-id="40097-115">In Group Policy settings for all versions of Windows 10, the notification feature is called **Enhanced notifications**.</span></span>

### <a name="use-group-policy-to-disable-additional-notifications"></a><span data-ttu-id="40097-116">Groepsbeleid gebruiken om extra meldingen uit te schakelen</span><span class="sxs-lookup"><span data-stu-id="40097-116">Use Group Policy to disable additional notifications</span></span>

1. <span data-ttu-id="40097-117">Open op uw computer voor groepsbeleidsbeheer de [Console groepsbeleidsbeheer](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="40097-117">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="40097-118">Klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en selecteer **bewerken.**</span><span class="sxs-lookup"><span data-stu-id="40097-118">Right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

3. <span data-ttu-id="40097-119">Ga in **de Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie.**</span><span class="sxs-lookup"><span data-stu-id="40097-119">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

4. <span data-ttu-id="40097-120">Selecteer **Beheersjablonen.**</span><span class="sxs-lookup"><span data-stu-id="40097-120">Select **Administrative templates**.</span></span>

5. <span data-ttu-id="40097-121">Vouw de structuur uit Windows **onderdelen**  >  **Microsoft Defender Antivirus** > Reporting\*\*.</span><span class="sxs-lookup"><span data-stu-id="40097-121">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > Reporting\*\*.</span></span>

6. <span data-ttu-id="40097-122">Dubbelklik op **Verbeterde meldingen uitschakelen** en stel de optie in op **Ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="40097-122">Double-click **Turn off enhanced notifications**, and set the option to **Enabled**.</span></span> <span data-ttu-id="40097-123">Selecteer vervolgens **OK**.</span><span class="sxs-lookup"><span data-stu-id="40097-123">Then select **OK**.</span></span> <span data-ttu-id="40097-124">Hierdoor worden er geen extra meldingen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="40097-124">This will prevent additional notifications from appearing.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="40097-125">Als u extra meldingen uit schakelt, worden kritieke meldingen niet uitgeschakeld, zoals waarschuwingen voor bedreigingsdetectie en herstel.</span><span class="sxs-lookup"><span data-stu-id="40097-125">Disabling additional notifications will not disable critical notifications, such as threat detection and remediation alerts.</span></span>

### <a name="use-the-windows-security-app-to-disable-additional-notifications"></a><span data-ttu-id="40097-126">Gebruik de Windows-beveiliging-app om extra meldingen uit te schakelen</span><span class="sxs-lookup"><span data-stu-id="40097-126">Use the Windows Security app to disable additional notifications</span></span>

1. <span data-ttu-id="40097-127">Open de Windows-beveiliging app door op het schildpictogram op de taakbalk te klikken of door te zoeken in het startmenu voor **beveiliging.**</span><span class="sxs-lookup"><span data-stu-id="40097-127">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Security**.</span></span>

2. <span data-ttu-id="40097-128">Selecteer **Tegel & bescherming** tegen virussen (of het schildpictogram op de linkermenubalk) en selecteer vervolgens Instellingen voor & **virusbeveiliging**</span><span class="sxs-lookup"><span data-stu-id="40097-128">Select **Virus & threat protection** tile (or the shield icon on the left menu bar) and, then select **Virus & threat protection settings**</span></span>

3. <span data-ttu-id="40097-129">Schuif naar de sectie Meldingen en selecteer **Meldingsinstellingen** **wijzigen.**</span><span class="sxs-lookup"><span data-stu-id="40097-129">Scroll to the **Notifications** section and select **Change notification settings**.</span></span>

4. <span data-ttu-id="40097-130">Schuif de schakelknop naar **Uit** of **Aan om** extra meldingen uit te schakelen of in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="40097-130">Slide the switch to **Off** or **On** to disable or enable additional notifications.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="40097-131">Als u extra meldingen uit schakelt, worden kritieke meldingen niet uitgeschakeld, zoals waarschuwingen voor bedreigingsdetectie en herstel.</span><span class="sxs-lookup"><span data-stu-id="40097-131">Disabling additional notifications will not disable critical notifications, such as threat detection and remediation alerts.</span></span>

## <a name="configure-standard-notifications-on-endpoints-using-group-policy"></a><span data-ttu-id="40097-132">Standaardmeldingen voor eindpunten configureren met groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="40097-132">Configure standard notifications on endpoints using Group Policy</span></span>

<span data-ttu-id="40097-133">U kunt groepsbeleid gebruiken om:</span><span class="sxs-lookup"><span data-stu-id="40097-133">You can use Group Policy to:</span></span>

- <span data-ttu-id="40097-134">Extra, aangepaste tekst weergeven op eindpunten wanneer de gebruiker een actie moet uitvoeren</span><span class="sxs-lookup"><span data-stu-id="40097-134">Display additional, customized text on endpoints when the user needs to perform an action</span></span>
- <span data-ttu-id="40097-135">Alle meldingen op eindpunten verbergen</span><span class="sxs-lookup"><span data-stu-id="40097-135">Hide all notifications on endpoints</span></span>
- <span data-ttu-id="40097-136">Rebootmeldingen op eindpunten verbergen</span><span class="sxs-lookup"><span data-stu-id="40097-136">Hide reboot notifications on endpoints</span></span>

<span data-ttu-id="40097-137">Het verbergen van meldingen kan handig zijn in situaties waarin u niet de hele interface Microsoft Defender Antivirus verbergen.</span><span class="sxs-lookup"><span data-stu-id="40097-137">Hiding notifications can be useful in situations where you can't hide the entire Microsoft Defender Antivirus interface.</span></span> <span data-ttu-id="40097-138">Zie [Voorkomen dat gebruikers de](prevent-end-user-interaction-microsoft-defender-antivirus.md) gebruikersinterface van de Microsoft Defender Antivirus zien of gebruiken voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="40097-138">See [Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface](prevent-end-user-interaction-microsoft-defender-antivirus.md) for more information.</span></span> <span data-ttu-id="40097-139">Meldingen verbergen vindt alleen plaats op eindpunten waarop het beleid is geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="40097-139">Hiding notifications will only occur on endpoints to which the policy has been deployed.</span></span> <span data-ttu-id="40097-140">Meldingen met betrekking tot acties die moeten worden ondernomen (zoals een herstart) worden nog steeds weergegeven op het Microsoft Endpoint Manager Endpoint Protection dashboard en [rapporten.](/configmgr/protect/deploy-use/monitor-endpoint-protection)</span><span class="sxs-lookup"><span data-stu-id="40097-140">Notifications related to actions that must be taken (such as a reboot) will still appear on the [Microsoft Endpoint Manager Endpoint Protection monitoring dashboard and reports](/configmgr/protect/deploy-use/monitor-endpoint-protection).</span></span> 

<span data-ttu-id="40097-141">Zie De app aanpassen Windows-beveiliging uw organisatie als u aangepaste contactgegevens wilt [toevoegen aan eindpuntmeldingen.](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)</span><span class="sxs-lookup"><span data-stu-id="40097-141">To add custom contact information to endpoint notifications, see [Customize the Windows Security app for your organization](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center).</span></span>

### <a name="use-group-policy-to-hide-notifications"></a><span data-ttu-id="40097-142">Groepsbeleid gebruiken om meldingen te verbergen</span><span class="sxs-lookup"><span data-stu-id="40097-142">Use Group Policy to hide notifications</span></span>

1. <span data-ttu-id="40097-143">Open op uw computer voor groepsbeleidsbeheer de [Console groepsbeleidsbeheer](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="40097-143">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="40097-144">Klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en selecteer **bewerken.**</span><span class="sxs-lookup"><span data-stu-id="40097-144">Right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

3. <span data-ttu-id="40097-145">Ga in **groepsbeleidsbeheereditor** naar **Computerconfiguratie** en selecteer vervolgens **Beheersjablonen.**</span><span class="sxs-lookup"><span data-stu-id="40097-145">In the **Group Policy Management Editor** go to **Computer configuration** and then select **Administrative templates**.</span></span>

4. <span data-ttu-id="40097-146">Vouw de structuur uit Windows **onderdelen**  >  **Microsoft Defender Antivirus**  >  **clientinterface.**</span><span class="sxs-lookup"><span data-stu-id="40097-146">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Client interface**.</span></span> 

5. <span data-ttu-id="40097-147">Dubbelklik op **Alle meldingen onderdrukken en** stel de optie in op **Ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="40097-147">Double-click **Suppress all notifications** and set the option to **Enabled**.</span></span> 

6. <span data-ttu-id="40097-148">Selecteer **OK**.</span><span class="sxs-lookup"><span data-stu-id="40097-148">Select **OK**.</span></span> <span data-ttu-id="40097-149">Hierdoor worden er geen extra meldingen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="40097-149">This will prevent additional notifications from appearing.</span></span>

### <a name="use-group-policy-to-hide-reboot-notifications"></a><span data-ttu-id="40097-150">Groepsbeleid gebruiken om opnieuw opstarten-meldingen te verbergen</span><span class="sxs-lookup"><span data-stu-id="40097-150">Use Group Policy to hide reboot notifications</span></span>

1. <span data-ttu-id="40097-151">Open op uw computer voor groepsbeleidsbeheer de [Console groepsbeleidsbeheer](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="40097-151">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="40097-152">Klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en selecteer **bewerken.**</span><span class="sxs-lookup"><span data-stu-id="40097-152">Right-click the Group Policy Object you want to configure and then select **Edit**.</span></span>

2. <span data-ttu-id="40097-153">Ga in **de Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie.**</span><span class="sxs-lookup"><span data-stu-id="40097-153">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="40097-154">Klik **op Beheersjablonen.**</span><span class="sxs-lookup"><span data-stu-id="40097-154">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="40097-155">Vouw de structuur uit Windows **onderdelen**  >  **Microsoft Defender Antivirus**  >  **clientinterface.**</span><span class="sxs-lookup"><span data-stu-id="40097-155">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Client interface**.</span></span>

5. <span data-ttu-id="40097-156">Dubbelklik op **Rebootmeldingen onderdrukken** en stel de optie in op **Ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="40097-156">Double-click **Suppresses reboot notifications** and set the option to **Enabled**.</span></span> 

5. <span data-ttu-id="40097-157">Selecteer **OK**.</span><span class="sxs-lookup"><span data-stu-id="40097-157">Select **OK**.</span></span> <span data-ttu-id="40097-158">Hierdoor worden er geen extra meldingen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="40097-158">This will prevent additional notifications from appearing.</span></span>

