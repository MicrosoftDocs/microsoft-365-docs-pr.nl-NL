---
title: De time-Microsoft Defender Antivirus voor cloudblokkering configureren
description: U kunt configureren hoe lang Microsoft Defender Antivirus een bestand kan worden uitgevoerd terwijl u wacht op een cloudbepaling.
keywords: Microsoft Defender Antivirus, antimalware, beveiliging, defender, cloud, time-out, blok, punt, seconden
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.date: 06/04/2021
ms.openlocfilehash: dfb75b77119d9550931c3e476323bde67a3b148f
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789085"
---
# <a name="configure-the-cloud-block-timeout-period"></a><span data-ttu-id="5785f-104">De time-outperiode voor cloudblokkering configureren</span><span class="sxs-lookup"><span data-stu-id="5785f-104">Configure the cloud block timeout period</span></span>

<span data-ttu-id="5785f-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="5785f-105">**Applies to:**</span></span>

- [<span data-ttu-id="5785f-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="5785f-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="5785f-107">Wanneer Microsoft Defender Antivirus een verdacht bestand vindt, kan het voorkomen dat het bestand wordt uitgevoerd terwijl de Microsoft Defender Antivirus [cloudservice wordt opgevraagd.](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="5785f-107">When Microsoft Defender Antivirus finds a suspicious file, it can prevent the file from running while it queries the [Microsoft Defender Antivirus cloud service](cloud-protection-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="5785f-108">De standaardperiode dat het bestand is [geblokkeerd,](configure-block-at-first-sight-microsoft-defender-antivirus.md) is 10 seconden.</span><span class="sxs-lookup"><span data-stu-id="5785f-108">The default period that the file is [blocked](configure-block-at-first-sight-microsoft-defender-antivirus.md) is 10 seconds.</span></span> <span data-ttu-id="5785f-109">Als u een beveiligingsbeheerder bent, kunt u meer tijd opgeven om te wachten voordat het bestand mag worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="5785f-109">If you're a security administrator, you can specify more time to wait before the file is allowed to run.</span></span> <span data-ttu-id="5785f-110">Door de time-outperiode voor cloudblokkering uit te breiden, kan ervoor worden gezorgd dat er voldoende tijd is om een juiste bepaling te ontvangen van de Microsoft Defender Antivirus cloudservice.</span><span class="sxs-lookup"><span data-stu-id="5785f-110">Extending the cloud block timeout period can help ensure there is enough time to receive a proper determination from the Microsoft Defender Antivirus cloud service.</span></span>

## <a name="prerequisites-to-use-the-extended-cloud-block-timeout"></a><span data-ttu-id="5785f-111">Vereisten voor het gebruik van de time-out voor uitgebreide cloudblokkering</span><span class="sxs-lookup"><span data-stu-id="5785f-111">Prerequisites to use the extended cloud block timeout</span></span>

<span data-ttu-id="5785f-112">[Blok op het eerste gezicht](configure-block-at-first-sight-microsoft-defender-antivirus.md) en de vereisten moeten zijn ingeschakeld voordat u een langere time-outperiode kunt opgeven.</span><span class="sxs-lookup"><span data-stu-id="5785f-112">[Block at first sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) and its prerequisites must be enabled before you can specify an extended timeout period.</span></span>

## <a name="specify-the-extended-timeout-period-using-microsoft-endpoint-manager"></a><span data-ttu-id="5785f-113">De verlengde time-outperiode opgeven met Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="5785f-113">Specify the extended timeout period using Microsoft Endpoint Manager</span></span>

<span data-ttu-id="5785f-114">U kunt de time-outperiode voor cloudblokkering opgeven met een [eindpuntbeveiligingsbeleid in Microsoft Endpoint Manager.](/mem/intune/protect/endpoint-security-policy)</span><span class="sxs-lookup"><span data-stu-id="5785f-114">You can specify the cloud block timeout period with an [endpoint security policy in Microsoft Endpoint Manager](/mem/intune/protect/endpoint-security-policy).</span></span>

1. <span data-ttu-id="5785f-115">Ga naar het Endpoint Manager [https://endpoint.microsoft.com/](https://endpoint.microsoft.com/) () en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="5785f-115">Go to the Endpoint Manager admin center ([https://endpoint.microsoft.com/](https://endpoint.microsoft.com/)) and sign in.</span></span>

2. <span data-ttu-id="5785f-116">Selecteer **Endpoint-beveiliging** en kies **vervolgens** onder Beheren de optie **Antivirus.**</span><span class="sxs-lookup"><span data-stu-id="5785f-116">Select **Endpoint security**, and then under **Manage**, choose **Antivirus**.</span></span>

3. <span data-ttu-id="5785f-117">Selecteer (of maak) een antivirusbeleid.</span><span class="sxs-lookup"><span data-stu-id="5785f-117">Select (or create) an antivirus policy.</span></span>

4. <span data-ttu-id="5785f-118">Vouw cloudbeveiliging uit in **de** sectie **Configuratie-instellingen.**</span><span class="sxs-lookup"><span data-stu-id="5785f-118">In the **Configuration settings** section, expand **Cloud protection**.</span></span> <span data-ttu-id="5785f-119">Geef vervolgens in **het vak Verlengde time-out in** seconden van de Defender Cloud de tijd in seconden op van 1 seconde naar 50 seconden.</span><span class="sxs-lookup"><span data-stu-id="5785f-119">Then, in the **Defender Cloud Extended Timeout In Seconds** box, specify the more time, in seconds, from 1 second to 50 seconds.</span></span> <span data-ttu-id="5785f-120">Wat u opgeeft, wordt toegevoegd aan de standaard 10 seconden.</span><span class="sxs-lookup"><span data-stu-id="5785f-120">Whatever you specify is added to the default 10 seconds.</span></span>

5. <span data-ttu-id="5785f-121">(Deze stap is optioneel) Andere wijzigingen aanbrengen in uw antivirusbeleid.</span><span class="sxs-lookup"><span data-stu-id="5785f-121">(This step is optional) Make any other changes to your antivirus policy.</span></span> <span data-ttu-id="5785f-122">(Hulp nodig?</span><span class="sxs-lookup"><span data-stu-id="5785f-122">(Need help?</span></span> <span data-ttu-id="5785f-123">Zie [Instellingen voor Microsoft Defender Antivirus beleid in Microsoft Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-windows).)</span><span class="sxs-lookup"><span data-stu-id="5785f-123">See [Settings for Microsoft Defender Antivirus policy in Microsoft Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-windows).)</span></span>

6. <span data-ttu-id="5785f-124">Kies **Volgende** en werk het configureren van uw beleid af.</span><span class="sxs-lookup"><span data-stu-id="5785f-124">Choose **Next**, and finish configuring your policy.</span></span>

## <a name="specify-the-extended-timeout-period-using-group-policy"></a><span data-ttu-id="5785f-125">De verlengde time-outperiode opgeven met groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="5785f-125">Specify the extended timeout period using Group Policy</span></span>

<span data-ttu-id="5785f-126">U kunt Groepsbeleid gebruiken om een uitgebreide time-out voor cloudcontroles op te geven.</span><span class="sxs-lookup"><span data-stu-id="5785f-126">You can use Group Policy to specify an extended timeout for cloud checks.</span></span>

1. <span data-ttu-id="5785f-127">Open op uw groepsbeleidscomputer de [console Groepsbeleidsbeheer](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="5785f-127">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))</span></span>

2. <span data-ttu-id="5785f-128">Klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en selecteer **bewerken.**</span><span class="sxs-lookup"><span data-stu-id="5785f-128">Right-click the Group Policy Object you want to configure and then select **Edit**.</span></span>

3. <span data-ttu-id="5785f-129">Ga in **de Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie** en selecteer vervolgens **Beheersjablonen.**</span><span class="sxs-lookup"><span data-stu-id="5785f-129">In the **Group Policy Management Editor**, go to **Computer configuration**, and then select **Administrative templates**.</span></span>

3. <span data-ttu-id="5785f-130">Vouw de boom uit Windows **onderdelen**  >  **Microsoft Defender Antivirus**  >  **MpEngine**.</span><span class="sxs-lookup"><span data-stu-id="5785f-130">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **MpEngine**.</span></span>

4. <span data-ttu-id="5785f-131">Dubbelklik op **Uitgebreide cloudcontrole configureren** en controleer of de optie is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="5785f-131">Double-click **Configure extended cloud check** and ensure the option is enabled.</span></span> 

   <span data-ttu-id="5785f-132">Geef de extra tijd op om te voorkomen dat het bestand wordt uitgevoerd terwijl u wacht op een cloudbepaling.</span><span class="sxs-lookup"><span data-stu-id="5785f-132">Specify the extra amount of time to prevent the file from running while waiting for a cloud determination.</span></span> <span data-ttu-id="5785f-133">Geef de extra tijd in seconden op van 1 seconde naar 50 seconden.</span><span class="sxs-lookup"><span data-stu-id="5785f-133">Specify the extra time, in seconds, from 1 second to 50 seconds.</span></span> <span data-ttu-id="5785f-134">Wat u opgeeft, wordt toegevoegd aan de standaard 10 seconden.</span><span class="sxs-lookup"><span data-stu-id="5785f-134">Whatever you specify is added to the default 10 seconds.</span></span>

5. <span data-ttu-id="5785f-135">Selecteer **OK**.</span><span class="sxs-lookup"><span data-stu-id="5785f-135">Select **OK**.</span></span>

 