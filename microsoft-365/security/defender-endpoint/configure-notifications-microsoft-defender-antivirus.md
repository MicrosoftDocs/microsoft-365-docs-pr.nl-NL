---
title: Microsoft Defender Antivirus meldingen configureren
description: Meer informatie over het configureren en aanpassen van zowel standaard- als aanvullende Microsoft Defender Antivirus meldingen op eindpunten.
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
ms.date: 05/17/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: f885b6d7991e4175cd14be5bbe9e0a7c96b1580f
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572343"
---
# <a name="configure-the-notifications-that-appear-on-endpoints"></a><span data-ttu-id="5cd6a-104">De meldingen configureren die op eindpunten worden weergegeven</span><span class="sxs-lookup"><span data-stu-id="5cd6a-104">Configure the notifications that appear on endpoints</span></span>

<span data-ttu-id="5cd6a-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="5cd6a-105">**Applies to:**</span></span>

- [<span data-ttu-id="5cd6a-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="5cd6a-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="5cd6a-107">In Windows 10 zijn toepassingsmeldingen over malwaredetectie en -herstel robuuster, consistenter en beknopter.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-107">In Windows 10, application notifications about malware detection and remediation are more robust, consistent, and concise.</span></span>

<span data-ttu-id="5cd6a-108">Meldingen worden weergegeven op eindpunten wanneer handmatig geactiveerde en geplande scans worden voltooid en bedreigingen worden gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-108">Notifications appear on endpoints when manually triggered and scheduled scans are completed and threats are detected.</span></span> <span data-ttu-id="5cd6a-109">Deze meldingen worden ook weergegeven in het **berichtencentrum** en er wordt regelmatig een overzicht van scans en bedreigingsdetecties weergegeven.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-109">These notifications also appear in the **Notification Center**, and a summary of scans and threat detections appear at regular time intervals.</span></span>

<span data-ttu-id="5cd6a-110">U kunt ook configureren hoe standaard meldingen worden weer geven op eind punten, zoals meldingen voor opnieuw opstarten of wanneer een bedreiging is gedetecteerd en hersteld.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-110">You can also configure how standard notifications appear on endpoints, such as notifications for reboot or when a threat has been detected and remediated.</span></span>

## <a name="configure-the-additional-notifications-that-appear-on-endpoints"></a><span data-ttu-id="5cd6a-111">De extra meldingen configureren die op eindpunten worden weergegeven</span><span class="sxs-lookup"><span data-stu-id="5cd6a-111">Configure the additional notifications that appear on endpoints</span></span>

<span data-ttu-id="5cd6a-112">U kunt de weergave van aanvullende meldingen, zoals recente samenvattingen van bedreigingsdetectie, configureren in de [Windows-beveiliging-app](microsoft-defender-security-center-antivirus.md) en met groepsbeleid.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-112">You can configure the display of additional notifications, such as recent threat detection summaries, in the [Windows Security app](microsoft-defender-security-center-antivirus.md) and with Group Policy.</span></span>

> [!NOTE]
> <span data-ttu-id="5cd6a-113">In Windows 10 versie 1607 werd de functie **Verbeterde meldingen** genoemd en kon worden geconfigureerd onder **Windows Instellingen** Update  >  **& beveiliging**  >  **Windows Defender**.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-113">In Windows 10, version 1607 the feature was called **Enhanced notifications** and could be configured under **Windows Settings** > **Update & security** > **Windows Defender**.</span></span> <span data-ttu-id="5cd6a-114">In groepsbeleidsinstellingen in alle versies van Windows 10 wordt dit **uitgebreide meldingen** genoemd.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-114">In Group Policy settings in all versions of Windows 10, it is called **Enhanced notifications**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5cd6a-115">Als u extra meldingen uitschakelt, worden kritieke meldingen, zoals waarschuwingen voor bedreigingsdetectie en herstel, niet uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-115">Disabling additional notifications will not disable critical notifications, such as threat detection and remediation alerts.</span></span>

<span data-ttu-id="5cd6a-116">**Gebruik de Windows-beveiliging-app om extra meldingen uit te schakelen:**</span><span class="sxs-lookup"><span data-stu-id="5cd6a-116">**Use the Windows Security app to disable additional notifications:**</span></span>

1. <span data-ttu-id="5cd6a-117">Open de Windows-beveiliging app door op het schildpictogram in de taakbalk te klikken of in het startmenu te zoeken naar **Beveiliging**.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-117">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Security**.</span></span>

2. <span data-ttu-id="5cd6a-118">Selecteer Virus & tegel **voor bedreigingsbeveiliging** (of het schildpictogram op de linkermenubalk) en selecteer vervolgens **Virus & instellingen voor bedreigingsbeveiliging**</span><span class="sxs-lookup"><span data-stu-id="5cd6a-118">Select **Virus & threat protection** tile (or the shield icon on the left menu bar) and, then select **Virus & threat protection settings**</span></span>

3. <span data-ttu-id="5cd6a-119">Scrol naar de sectie **Meldingen** en klik op **Meldingsinstellingen wijzigen**.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-119">Scroll to the **Notifications** section and click **Change notification settings**.</span></span>

4. <span data-ttu-id="5cd6a-120">Schuif de schakelaar naar **Uit** of **Aan** om extra meldingen uit of in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-120">Slide the switch to **Off** or **On** to disable or enable additional notifications.</span></span>

<span data-ttu-id="5cd6a-121">**Groepsbeleid gebruiken om aanvullende meldingen uit te schakelen:**</span><span class="sxs-lookup"><span data-stu-id="5cd6a-121">**Use Group Policy to disable additional notifications:**</span></span>

1. <span data-ttu-id="5cd6a-122">Open op de computer voor groepsbeleidsbeheer de [Console voor groepsbeleidsbeheer](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))en klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik op **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-122">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="5cd6a-123">Ga in de **Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie**.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-123">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="5cd6a-124">Klik **op Beheersjablonen**.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-124">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="5cd6a-125">Vouw de structuur uit om **onderdelen > Microsoft Defender Antivirus > rapportage te Windows.**</span><span class="sxs-lookup"><span data-stu-id="5cd6a-125">Expand the tree to **Windows components > Microsoft Defender Antivirus > Reporting**.</span></span>

5. <span data-ttu-id="5cd6a-126">Dubbelklik op **Verbeterde meldingen uitschakelen** en stel de optie in op **Ingeschakeld**.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-126">Double-click **Turn off enhanced notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="5cd6a-127">Klik op **OK**.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-127">Click **OK**.</span></span> <span data-ttu-id="5cd6a-128">Dit voorkomt dat er extra meldingen verschijnen.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-128">This will prevent additional notifications from appearing.</span></span>

## <a name="configure-standard-notifications-on-endpoints"></a><span data-ttu-id="5cd6a-129">Standaardmeldingen op eindpunten configureren</span><span class="sxs-lookup"><span data-stu-id="5cd6a-129">Configure standard notifications on endpoints</span></span>

<span data-ttu-id="5cd6a-130">U kunt groepsbeleid gebruiken om:</span><span class="sxs-lookup"><span data-stu-id="5cd6a-130">You can use Group Policy to:</span></span>

- <span data-ttu-id="5cd6a-131">Extra, aangepaste tekst weergeven op eindpunten wanneer de gebruiker een actie moet uitvoeren</span><span class="sxs-lookup"><span data-stu-id="5cd6a-131">Display additional, customized text on endpoints when the user needs to perform an action</span></span>
- <span data-ttu-id="5cd6a-132">Alle meldingen op eindpunten verbergen</span><span class="sxs-lookup"><span data-stu-id="5cd6a-132">Hide all notifications on endpoints</span></span>
- <span data-ttu-id="5cd6a-133">Herstartmeldingen op eindpunten verbergen</span><span class="sxs-lookup"><span data-stu-id="5cd6a-133">Hide reboot notifications on endpoints</span></span>

<span data-ttu-id="5cd6a-134">Het verbergen van meldingen kan handig zijn in situaties waarin u niet de hele Microsoft Defender Antivirus interface kunt verbergen.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-134">Hiding notifications can be useful in situations where you can't hide the entire Microsoft Defender Antivirus interface.</span></span> <span data-ttu-id="5cd6a-135">Zie [Voorkomen dat gebruikers de Microsoft Defender Antivirus gebruikersinterface zien of ermee communiceren](prevent-end-user-interaction-microsoft-defender-antivirus.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-135">See [Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface](prevent-end-user-interaction-microsoft-defender-antivirus.md) for more information.</span></span> 

> [!NOTE]
> <span data-ttu-id="5cd6a-136">Het verbergen van meldingen vindt alleen plaats op eindpunten waarop het beleid is geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-136">Hiding notifications will only occur on endpoints to which the policy has been deployed.</span></span> <span data-ttu-id="5cd6a-137">Meldingen met betrekking tot acties die moeten worden uitgevoerd (zoals opnieuw opstarten) worden nog steeds weergegeven op het [Microsoft Endpoint Manager Endpoint Protection monitoringdashboard en rapporten](/configmgr/protect/deploy-use/monitor-endpoint-protection).</span><span class="sxs-lookup"><span data-stu-id="5cd6a-137">Notifications related to actions that must be taken (such as a reboot) will still appear on the [Microsoft Endpoint Manager Endpoint Protection monitoring dashboard and reports](/configmgr/protect/deploy-use/monitor-endpoint-protection).</span></span> 

<span data-ttu-id="5cd6a-138">Zie [De Windows-beveiliging-app voor uw organisatie aanpassen](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) voor instructies om aangepaste contactgegevens toe te voegen aan de meldingen die gebruikers op hun machines zien.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-138">See [Customize the Windows Security app for your organization](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) for instructions to add custom contact information to the notifications that users see on their machines.</span></span>

<span data-ttu-id="5cd6a-139">**Groepsbeleid gebruiken om meldingen te verbergen:**</span><span class="sxs-lookup"><span data-stu-id="5cd6a-139">**Use Group Policy to hide notifications:**</span></span>

1. <span data-ttu-id="5cd6a-140">Open op de computer voor groepsbeleidsbeheer de [Console voor groepsbeleidsbeheer](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))en klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik op **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-140">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure, and click **Edit**.</span></span>

2. <span data-ttu-id="5cd6a-141">Ga in de **Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie** en klik op **Beheersjablonen**.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-141">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="5cd6a-142">Vouw de structuur uit om **onderdelen > Microsoft Defender Antivirus > clientinterface te Windows.**</span><span class="sxs-lookup"><span data-stu-id="5cd6a-142">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span> 

4. <span data-ttu-id="5cd6a-143">Dubbelklik op **Alle meldingen onderdrukken** en stel de optie in op **Ingeschakeld**.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-143">Double-click **Suppress all notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="5cd6a-144">Klik op **OK**.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-144">Click **OK**.</span></span> <span data-ttu-id="5cd6a-145">Dit voorkomt dat er extra meldingen verschijnen.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-145">This will prevent additional notifications from appearing.</span></span>

<span data-ttu-id="5cd6a-146">**Groepsbeleid gebruiken om herstartmeldingen te verbergen:**</span><span class="sxs-lookup"><span data-stu-id="5cd6a-146">**Use Group Policy to hide reboot notifications:**</span></span>

1. <span data-ttu-id="5cd6a-147">Open op de computer voor groepsbeleidsbeheer de [Console voor groepsbeleidsbeheer](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))en klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik op **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-147">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="5cd6a-148">Ga in de **Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie**.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-148">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="5cd6a-149">Klik **op Beheersjablonen**.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-149">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="5cd6a-150">Vouw de structuur uit om **onderdelen > Microsoft Defender Antivirus > clientinterface te Windows.**</span><span class="sxs-lookup"><span data-stu-id="5cd6a-150">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span>

5. <span data-ttu-id="5cd6a-151">Dubbelklik op **Opnieuw opstarten van meldingen onderdrukken** en stel de optie in op **Ingeschakeld**.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-151">Double-click **Suppresses reboot notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="5cd6a-152">Klik op **OK**.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-152">Click **OK**.</span></span> <span data-ttu-id="5cd6a-153">Dit voorkomt dat er extra meldingen verschijnen.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-153">This will prevent additional notifications from appearing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="5cd6a-154">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="5cd6a-154">Related topics</span></span>

- [<span data-ttu-id="5cd6a-155">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="5cd6a-155">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="5cd6a-156">Interactie van eindgebruikers met Microsoft Defender Antivirus configureren</span><span class="sxs-lookup"><span data-stu-id="5cd6a-156">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md)
