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
ms.date: 05/17/2021
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: 1e9f733b20b62af7e73a923932057920ff1dc155
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926236"
---
# <a name="configure-the-notifications-that-appear-on-endpoints"></a><span data-ttu-id="8d089-104">De meldingen configureren die worden weergegeven op eindpunten</span><span class="sxs-lookup"><span data-stu-id="8d089-104">Configure the notifications that appear on endpoints</span></span>

<span data-ttu-id="8d089-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="8d089-105">**Applies to:**</span></span>

- [<span data-ttu-id="8d089-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="8d089-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="8d089-107">In Windows 10 zijn toepassingsmeldingen over malwaredetectie en -herstel krachtiger, consistenter en beknopter.</span><span class="sxs-lookup"><span data-stu-id="8d089-107">In Windows 10, application notifications about malware detection and remediation are more robust, consistent, and concise.</span></span>

<span data-ttu-id="8d089-108">Meldingen worden weergegeven op eindpunten wanneer handmatig geactiveerde en geplande scans worden voltooid en bedreigingen worden gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="8d089-108">Notifications appear on endpoints when manually triggered and scheduled scans are completed and threats are detected.</span></span> <span data-ttu-id="8d089-109">Deze meldingen worden ook weergegeven in het **systeemmeldingscentrum** en er wordt regelmatig een overzicht van scans en bedreigingsdetecties weergegeven.</span><span class="sxs-lookup"><span data-stu-id="8d089-109">These notifications also appear in the **Notification Center**, and a summary of scans and threat detections appear at regular time intervals.</span></span>

<span data-ttu-id="8d089-110">U kunt ook configureren hoe standaardmeldingen worden weergegeven op eindpunten, zoals meldingen voor het opnieuw opstarten of wanneer een bedreiging is gedetecteerd en geremediat.</span><span class="sxs-lookup"><span data-stu-id="8d089-110">You can also configure how standard notifications appear on endpoints, such as notifications for reboot or when a threat has been detected and remediated.</span></span>

## <a name="configure-the-additional-notifications-that-appear-on-endpoints"></a><span data-ttu-id="8d089-111">De extra meldingen configureren die op eindpunten worden weergegeven</span><span class="sxs-lookup"><span data-stu-id="8d089-111">Configure the additional notifications that appear on endpoints</span></span>

<span data-ttu-id="8d089-112">U kunt de weergave van extra meldingen, zoals recente samenvattingen voor bedreigingsdetectie, configureren in de Windows-beveiliging [app](microsoft-defender-security-center-antivirus.md) en met groepsbeleid.</span><span class="sxs-lookup"><span data-stu-id="8d089-112">You can configure the display of additional notifications, such as recent threat detection summaries, in the [Windows Security app](microsoft-defender-security-center-antivirus.md) and with Group Policy.</span></span>

> [!NOTE]
> <span data-ttu-id="8d089-113">In Windows 10 versie 1607 werd de functie **Enhanced notifications** genoemd en kon deze worden geconfigureerd onder **Windows Instellingen**  >  **Update &**  >  **beveiligingsinstellingen Windows Defender.**</span><span class="sxs-lookup"><span data-stu-id="8d089-113">In Windows 10, version 1607 the feature was called **Enhanced notifications** and could be configured under **Windows Settings** > **Update & security** > **Windows Defender**.</span></span> <span data-ttu-id="8d089-114">In groepsbeleidsinstellingen in alle versies van Windows 10, wordt dit **enhanced notifications genoemd.**</span><span class="sxs-lookup"><span data-stu-id="8d089-114">In Group Policy settings in all versions of Windows 10, it is called **Enhanced notifications**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8d089-115">Als u extra meldingen uit schakelt, worden kritieke meldingen niet uitgeschakeld, zoals waarschuwingen voor bedreigingsdetectie en herstel.</span><span class="sxs-lookup"><span data-stu-id="8d089-115">Disabling additional notifications will not disable critical notifications, such as threat detection and remediation alerts.</span></span>

<span data-ttu-id="8d089-116">**Gebruik de Windows-beveiliging app om extra meldingen uit te schakelen:**</span><span class="sxs-lookup"><span data-stu-id="8d089-116">**Use the Windows Security app to disable additional notifications:**</span></span>

1. <span data-ttu-id="8d089-117">Open de Windows-beveiliging app door op het schildpictogram op de taakbalk te klikken of door te zoeken in het startmenu voor **beveiliging.**</span><span class="sxs-lookup"><span data-stu-id="8d089-117">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Security**.</span></span>

2. <span data-ttu-id="8d089-118">Selecteer **Tegel & bescherming** tegen virussen (of het schildpictogram op de linkermenubalk) en selecteer vervolgens Instellingen voor & **virusbeveiliging**</span><span class="sxs-lookup"><span data-stu-id="8d089-118">Select **Virus & threat protection** tile (or the shield icon on the left menu bar) and, then select **Virus & threat protection settings**</span></span>

3. <span data-ttu-id="8d089-119">Schuif naar de sectie Meldingen en klik op **Meldingsinstellingen** **wijzigen.**</span><span class="sxs-lookup"><span data-stu-id="8d089-119">Scroll to the **Notifications** section and click **Change notification settings**.</span></span>

4. <span data-ttu-id="8d089-120">Schuif de schakelknop naar **Uit** of **Aan om** extra meldingen uit te schakelen of in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="8d089-120">Slide the switch to **Off** or **On** to disable or enable additional notifications.</span></span>

<span data-ttu-id="8d089-121">**Groepsbeleid gebruiken om extra meldingen uit te schakelen:**</span><span class="sxs-lookup"><span data-stu-id="8d089-121">**Use Group Policy to disable additional notifications:**</span></span>

1. <span data-ttu-id="8d089-122">Open op de computer groepsbeleidsbeheer de console Groepsbeleidsbeheer, [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik op **Bewerken.**</span><span class="sxs-lookup"><span data-stu-id="8d089-122">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="8d089-123">Ga in **de Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie.**</span><span class="sxs-lookup"><span data-stu-id="8d089-123">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="8d089-124">Klik **op Beheersjablonen.**</span><span class="sxs-lookup"><span data-stu-id="8d089-124">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="8d089-125">Vouw de structuur uit Windows **onderdelen > Microsoft Defender Antivirus > Reporting.**</span><span class="sxs-lookup"><span data-stu-id="8d089-125">Expand the tree to **Windows components > Microsoft Defender Antivirus > Reporting**.</span></span>

5. <span data-ttu-id="8d089-126">Dubbelklik op **Verbeterde meldingen uitschakelen** en stel de optie in op **Ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="8d089-126">Double-click **Turn off enhanced notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="8d089-127">Klik op **OK**.</span><span class="sxs-lookup"><span data-stu-id="8d089-127">Click **OK**.</span></span> <span data-ttu-id="8d089-128">Hierdoor worden er geen extra meldingen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="8d089-128">This will prevent additional notifications from appearing.</span></span>

## <a name="configure-standard-notifications-on-endpoints"></a><span data-ttu-id="8d089-129">Standaardmeldingen voor eindpunten configureren</span><span class="sxs-lookup"><span data-stu-id="8d089-129">Configure standard notifications on endpoints</span></span>

<span data-ttu-id="8d089-130">U kunt groepsbeleid gebruiken om:</span><span class="sxs-lookup"><span data-stu-id="8d089-130">You can use Group Policy to:</span></span>

- <span data-ttu-id="8d089-131">Extra, aangepaste tekst weergeven op eindpunten wanneer de gebruiker een actie moet uitvoeren</span><span class="sxs-lookup"><span data-stu-id="8d089-131">Display additional, customized text on endpoints when the user needs to perform an action</span></span>
- <span data-ttu-id="8d089-132">Alle meldingen op eindpunten verbergen</span><span class="sxs-lookup"><span data-stu-id="8d089-132">Hide all notifications on endpoints</span></span>
- <span data-ttu-id="8d089-133">Rebootmeldingen op eindpunten verbergen</span><span class="sxs-lookup"><span data-stu-id="8d089-133">Hide reboot notifications on endpoints</span></span>

<span data-ttu-id="8d089-134">Het verbergen van meldingen kan handig zijn in situaties waarin u niet de hele interface Microsoft Defender Antivirus verbergen.</span><span class="sxs-lookup"><span data-stu-id="8d089-134">Hiding notifications can be useful in situations where you can't hide the entire Microsoft Defender Antivirus interface.</span></span> <span data-ttu-id="8d089-135">Zie [Voorkomen dat gebruikers de](prevent-end-user-interaction-microsoft-defender-antivirus.md) gebruikersinterface van de Microsoft Defender Antivirus zien of gebruiken voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="8d089-135">See [Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface](prevent-end-user-interaction-microsoft-defender-antivirus.md) for more information.</span></span> 

> [!NOTE]
> <span data-ttu-id="8d089-136">Meldingen verbergen vindt alleen plaats op eindpunten waarop het beleid is geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="8d089-136">Hiding notifications will only occur on endpoints to which the policy has been deployed.</span></span> <span data-ttu-id="8d089-137">Meldingen met betrekking tot acties die moeten worden ondernomen (zoals een herstart) worden nog steeds weergegeven op het Microsoft Endpoint Manager Endpoint Protection dashboard en [rapporten.](/configmgr/protect/deploy-use/monitor-endpoint-protection)</span><span class="sxs-lookup"><span data-stu-id="8d089-137">Notifications related to actions that must be taken (such as a reboot) will still appear on the [Microsoft Endpoint Manager Endpoint Protection monitoring dashboard and reports](/configmgr/protect/deploy-use/monitor-endpoint-protection).</span></span> 

<span data-ttu-id="8d089-138">Zie [De app Windows-beveiliging voor](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) uw organisatie aanpassen voor instructies voor het toevoegen van aangepaste contactgegevens aan de meldingen die gebruikers op hun machines zien.</span><span class="sxs-lookup"><span data-stu-id="8d089-138">See [Customize the Windows Security app for your organization](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) for instructions to add custom contact information to the notifications that users see on their machines.</span></span>

<span data-ttu-id="8d089-139">**Groepsbeleid gebruiken om meldingen te verbergen:**</span><span class="sxs-lookup"><span data-stu-id="8d089-139">**Use Group Policy to hide notifications:**</span></span>

1. <span data-ttu-id="8d089-140">Open op de computer groepsbeleidsbeheer de console Groepsbeleidsbeheer, klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik op **Bewerken.** [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="8d089-140">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure, and click **Edit**.</span></span>

2. <span data-ttu-id="8d089-141">Ga in **groepsbeleidseditor** naar **Computerconfiguratie** en klik op **Beheersjablonen.**</span><span class="sxs-lookup"><span data-stu-id="8d089-141">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="8d089-142">Vouw de structuur uit **Windows onderdelen > Microsoft Defender Antivirus > clientinterface.**</span><span class="sxs-lookup"><span data-stu-id="8d089-142">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span> 

4. <span data-ttu-id="8d089-143">Dubbelklik op **Alle meldingen onderdrukken en** stel de optie in op **Ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="8d089-143">Double-click **Suppress all notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="8d089-144">Klik op **OK**.</span><span class="sxs-lookup"><span data-stu-id="8d089-144">Click **OK**.</span></span> <span data-ttu-id="8d089-145">Hierdoor worden er geen extra meldingen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="8d089-145">This will prevent additional notifications from appearing.</span></span>

<span data-ttu-id="8d089-146">**Groepsbeleid gebruiken om opnieuw opstarten-meldingen te verbergen:**</span><span class="sxs-lookup"><span data-stu-id="8d089-146">**Use Group Policy to hide reboot notifications:**</span></span>

1. <span data-ttu-id="8d089-147">Open op de computer groepsbeleidsbeheer de console Groepsbeleidsbeheer, [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik op **Bewerken.**</span><span class="sxs-lookup"><span data-stu-id="8d089-147">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="8d089-148">Ga in **de Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie.**</span><span class="sxs-lookup"><span data-stu-id="8d089-148">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="8d089-149">Klik **op Beheersjablonen.**</span><span class="sxs-lookup"><span data-stu-id="8d089-149">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="8d089-150">Vouw de structuur uit **Windows onderdelen > Microsoft Defender Antivirus > clientinterface.**</span><span class="sxs-lookup"><span data-stu-id="8d089-150">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span>

5. <span data-ttu-id="8d089-151">Dubbelklik op **Rebootmeldingen onderdrukken** en stel de optie in op **Ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="8d089-151">Double-click **Suppresses reboot notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="8d089-152">Klik op **OK**.</span><span class="sxs-lookup"><span data-stu-id="8d089-152">Click **OK**.</span></span> <span data-ttu-id="8d089-153">Hierdoor worden er geen extra meldingen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="8d089-153">This will prevent additional notifications from appearing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8d089-154">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="8d089-154">Related topics</span></span>

- [<span data-ttu-id="8d089-155">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="8d089-155">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="8d089-156">Interactie tussen eindgebruikers configureren met Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="8d089-156">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md)
