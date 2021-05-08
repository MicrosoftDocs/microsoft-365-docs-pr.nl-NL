---
title: Microsoft Defender Antivirusmeldingen configureren
description: Meer informatie over het configureren en aanpassen van zowel standaard- als aanvullende Microsoft Defender Antivirusmeldingen op eindpunten.
keywords: meldingen, defender, antivirus, eindpunt, beheer, beheerder
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
ms.openlocfilehash: 6e11c9394f250a6f3882183224f53954b1390a23
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274626"
---
# <a name="configure-the-notifications-that-appear-on-endpoints"></a><span data-ttu-id="39956-104">De meldingen configureren die op eindpunten worden weergegeven</span><span class="sxs-lookup"><span data-stu-id="39956-104">Configure the notifications that appear on endpoints</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="39956-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="39956-105">**Applies to:**</span></span>

- [<span data-ttu-id="39956-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="39956-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="39956-107">In Windows 10 zijn toepassingsmeldingen over malwaredetectie en -herstel krachtiger, consistenter en beknopter.</span><span class="sxs-lookup"><span data-stu-id="39956-107">In Windows 10, application notifications about malware detection and remediation are more robust, consistent, and concise.</span></span>

<span data-ttu-id="39956-108">Meldingen worden weergegeven op eindpunten wanneer handmatig geactiveerde en geplande scans worden voltooid en bedreigingen worden gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="39956-108">Notifications appear on endpoints when manually triggered and scheduled scans are completed and threats are detected.</span></span> <span data-ttu-id="39956-109">Deze meldingen worden ook weergegeven in het **systeemmeldingscentrum** en er wordt regelmatig een overzicht van scans en bedreigingsdetecties weergegeven.</span><span class="sxs-lookup"><span data-stu-id="39956-109">These notifications also appear in the **Notification Center**, and a summary of scans and threat detections appear at regular time intervals.</span></span>

<span data-ttu-id="39956-110">U kunt ook configureren hoe standaardmeldingen worden weergegeven op eindpunten, zoals meldingen voor het opnieuw opstarten of wanneer een bedreiging is gedetecteerd en geremediat.</span><span class="sxs-lookup"><span data-stu-id="39956-110">You can also configure how standard notifications appear on endpoints, such as notifications for reboot or when a threat has been detected and remediated.</span></span>

## <a name="configure-the-additional-notifications-that-appear-on-endpoints"></a><span data-ttu-id="39956-111">De extra meldingen configureren die op eindpunten worden weergegeven</span><span class="sxs-lookup"><span data-stu-id="39956-111">Configure the additional notifications that appear on endpoints</span></span>

<span data-ttu-id="39956-112">U kunt de weergave van extra meldingen, zoals recente samenvattingen van bedreigingsdetectie, configureren in de [Windows-beveiligings-app](microsoft-defender-security-center-antivirus.md) en met groepsbeleid.</span><span class="sxs-lookup"><span data-stu-id="39956-112">You can configure the display of additional notifications, such as recent threat detection summaries, in the [Windows Security app](microsoft-defender-security-center-antivirus.md) and with Group Policy.</span></span>

> [!NOTE]
> <span data-ttu-id="39956-113">In Windows 10, versie 1607, werd de functie **Enhanced notifications** genoemd en kon deze worden geconfigureerd onder **Windows Settings**  >  **Update & security** Windows  >  **Defender**.</span><span class="sxs-lookup"><span data-stu-id="39956-113">In Windows 10, version 1607 the feature was called **Enhanced notifications** and could be configured under **Windows Settings** > **Update & security** > **Windows Defender**.</span></span> <span data-ttu-id="39956-114">In groepsbeleidsinstellingen in alle versies van Windows 10 wordt dit **enhanced notifications genoemd.**</span><span class="sxs-lookup"><span data-stu-id="39956-114">In Group Policy settings in all versions of Windows 10, it is called **Enhanced notifications**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="39956-115">Als u extra meldingen uit schakelt, worden kritieke meldingen niet uitgeschakeld, zoals waarschuwingen voor bedreigingsdetectie en herstel.</span><span class="sxs-lookup"><span data-stu-id="39956-115">Disabling additional notifications will not disable critical notifications, such as threat detection and remediation alerts.</span></span>

<span data-ttu-id="39956-116">**Gebruik de Windows Security-app om extra meldingen uit te schakelen:**</span><span class="sxs-lookup"><span data-stu-id="39956-116">**Use the Windows Security app to disable additional notifications:**</span></span>

1. <span data-ttu-id="39956-117">Open de Windows Security-app door op het schildpictogram op de taakbalk te klikken of door te zoeken in het startmenu voor **Defender.**</span><span class="sxs-lookup"><span data-stu-id="39956-117">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="39956-118">Klik op **de tegel & bescherming** tegen bedreigingen (of het schildpictogram op de linkermenubalk) en klik vervolgens op het label & instellingen voor **bedreigingsbeveiliging:**</span><span class="sxs-lookup"><span data-stu-id="39956-118">Click the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then the **Virus & threat protection settings** label:</span></span>

    ![Schermafbeelding van het label & beveiligingsinstellingen voor virussen in de Windows Security-app](images/defender/wdav-protection-settings-wdsc.png)

3. <span data-ttu-id="39956-120">Schuif naar de sectie Meldingen en klik op **Meldingsinstellingen** **wijzigen.**</span><span class="sxs-lookup"><span data-stu-id="39956-120">Scroll to the **Notifications** section and click **Change notification settings**.</span></span>

4. <span data-ttu-id="39956-121">Schuif de schakelknop naar **Uit** of **Aan om** extra meldingen uit te schakelen of in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="39956-121">Slide the switch to **Off** or **On** to disable or enable additional notifications.</span></span>

<span data-ttu-id="39956-122">**Groepsbeleid gebruiken om extra meldingen uit te schakelen:**</span><span class="sxs-lookup"><span data-stu-id="39956-122">**Use Group Policy to disable additional notifications:**</span></span>

1. <span data-ttu-id="39956-123">Open op de computer groepsbeleidsbeheer de console Groepsbeleidsbeheer, [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik op **Bewerken.**</span><span class="sxs-lookup"><span data-stu-id="39956-123">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="39956-124">Ga in **de Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie.**</span><span class="sxs-lookup"><span data-stu-id="39956-124">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="39956-125">Klik **op Beheersjablonen.**</span><span class="sxs-lookup"><span data-stu-id="39956-125">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="39956-126">Vouw de structuur uit naar **Windows-onderdelen > Microsoft Defender Antivirus > Reporting**.</span><span class="sxs-lookup"><span data-stu-id="39956-126">Expand the tree to **Windows components > Microsoft Defender Antivirus > Reporting**.</span></span>

5. <span data-ttu-id="39956-127">Dubbelklik op **Verbeterde meldingen uitschakelen** en stel de optie in op **Ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="39956-127">Double-click **Turn off enhanced notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="39956-128">Klik op **OK**.</span><span class="sxs-lookup"><span data-stu-id="39956-128">Click **OK**.</span></span> <span data-ttu-id="39956-129">Hierdoor worden er geen extra meldingen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="39956-129">This will prevent additional notifications from appearing.</span></span>

## <a name="configure-standard-notifications-on-endpoints"></a><span data-ttu-id="39956-130">Standaardmeldingen voor eindpunten configureren</span><span class="sxs-lookup"><span data-stu-id="39956-130">Configure standard notifications on endpoints</span></span>

<span data-ttu-id="39956-131">U kunt groepsbeleid gebruiken om:</span><span class="sxs-lookup"><span data-stu-id="39956-131">You can use Group Policy to:</span></span>

- <span data-ttu-id="39956-132">Extra, aangepaste tekst weergeven op eindpunten wanneer de gebruiker een actie moet uitvoeren</span><span class="sxs-lookup"><span data-stu-id="39956-132">Display additional, customized text on endpoints when the user needs to perform an action</span></span>
- <span data-ttu-id="39956-133">Alle meldingen op eindpunten verbergen</span><span class="sxs-lookup"><span data-stu-id="39956-133">Hide all notifications on endpoints</span></span>
- <span data-ttu-id="39956-134">Rebootmeldingen op eindpunten verbergen</span><span class="sxs-lookup"><span data-stu-id="39956-134">Hide reboot notifications on endpoints</span></span>

<span data-ttu-id="39956-135">Het verbergen van meldingen kan handig zijn in situaties waarin u de volledige Microsoft Defender Antivirus-interface niet kunt verbergen.</span><span class="sxs-lookup"><span data-stu-id="39956-135">Hiding notifications can be useful in situations where you can't hide the entire Microsoft Defender Antivirus interface.</span></span> <span data-ttu-id="39956-136">Zie [Voorkomen dat gebruikers de](prevent-end-user-interaction-microsoft-defender-antivirus.md) gebruikersinterface van Microsoft Defender Antivirus kunnen zien of gebruiken voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="39956-136">See [Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface](prevent-end-user-interaction-microsoft-defender-antivirus.md) for more information.</span></span> 

> [!NOTE]
> <span data-ttu-id="39956-137">Meldingen verbergen vindt alleen plaats op eindpunten waarop het beleid is geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="39956-137">Hiding notifications will only occur on endpoints to which the policy has been deployed.</span></span> <span data-ttu-id="39956-138">Meldingen met betrekking tot acties die moeten worden ondernomen (zoals een herstart) worden nog steeds weergegeven op het dashboard en rapporten van [Endpoint Manager Endpoint Protection](/configmgr/protect/deploy-use/monitor-endpoint-protection)van Microsoft.</span><span class="sxs-lookup"><span data-stu-id="39956-138">Notifications related to actions that must be taken (such as a reboot) will still appear on the [Microsoft Endpoint Manager Endpoint Protection monitoring dashboard and reports](/configmgr/protect/deploy-use/monitor-endpoint-protection).</span></span> 

<span data-ttu-id="39956-139">Zie [De Windows Security-app voor uw](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) organisatie aanpassen voor instructies voor het toevoegen van aangepaste contactgegevens aan de meldingen die gebruikers op hun machines zien.</span><span class="sxs-lookup"><span data-stu-id="39956-139">See [Customize the Windows Security app for your organization](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) for instructions to add custom contact information to the notifications that users see on their machines.</span></span>

<span data-ttu-id="39956-140">**Groepsbeleid gebruiken om meldingen te verbergen:**</span><span class="sxs-lookup"><span data-stu-id="39956-140">**Use Group Policy to hide notifications:**</span></span>

1. <span data-ttu-id="39956-141">Open op de computer groepsbeleidsbeheer de console Groepsbeleidsbeheer, klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik op **Bewerken.** [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="39956-141">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure, and click **Edit**.</span></span>

2. <span data-ttu-id="39956-142">Ga in **groepsbeleidseditor** naar **Computerconfiguratie** en klik op **Beheersjablonen.**</span><span class="sxs-lookup"><span data-stu-id="39956-142">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="39956-143">Vouw de structuur uit naar **Windows-onderdelen > Microsoft Defender Antivirus > clientinterface.**</span><span class="sxs-lookup"><span data-stu-id="39956-143">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span> 

4. <span data-ttu-id="39956-144">Dubbelklik op **Alle meldingen onderdrukken en** stel de optie in op **Ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="39956-144">Double-click **Suppress all notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="39956-145">Klik op **OK**.</span><span class="sxs-lookup"><span data-stu-id="39956-145">Click **OK**.</span></span> <span data-ttu-id="39956-146">Hierdoor worden er geen extra meldingen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="39956-146">This will prevent additional notifications from appearing.</span></span>

<span data-ttu-id="39956-147">**Groepsbeleid gebruiken om opnieuw opstarten-meldingen te verbergen:**</span><span class="sxs-lookup"><span data-stu-id="39956-147">**Use Group Policy to hide reboot notifications:**</span></span>

1. <span data-ttu-id="39956-148">Open op de computer groepsbeleidsbeheer de console Groepsbeleidsbeheer, [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik op **Bewerken.**</span><span class="sxs-lookup"><span data-stu-id="39956-148">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="39956-149">Ga in **de Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie.**</span><span class="sxs-lookup"><span data-stu-id="39956-149">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="39956-150">Klik **op Beheersjablonen.**</span><span class="sxs-lookup"><span data-stu-id="39956-150">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="39956-151">Vouw de structuur uit naar **Windows-onderdelen > Microsoft Defender Antivirus > clientinterface.**</span><span class="sxs-lookup"><span data-stu-id="39956-151">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span>

5. <span data-ttu-id="39956-152">Dubbelklik op **Rebootmeldingen onderdrukken** en stel de optie in op **Ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="39956-152">Double-click **Suppresses reboot notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="39956-153">Klik op **OK**.</span><span class="sxs-lookup"><span data-stu-id="39956-153">Click **OK**.</span></span> <span data-ttu-id="39956-154">Hierdoor worden er geen extra meldingen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="39956-154">This will prevent additional notifications from appearing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="39956-155">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="39956-155">Related topics</span></span>

- [<span data-ttu-id="39956-156">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="39956-156">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="39956-157">Interactie tussen eindgebruikers configureren met Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="39956-157">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md)