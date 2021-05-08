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
ms.openlocfilehash: 02b8ee1c73116718d771847a43d6334e0723bd5c
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275303"
---
# <a name="configure-the-cloud-block-timeout-period"></a><span data-ttu-id="795b3-104">De time-outperiode voor cloudblokkering configureren</span><span class="sxs-lookup"><span data-stu-id="795b3-104">Configure the cloud block timeout period</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="795b3-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="795b3-105">**Applies to:**</span></span>

- [<span data-ttu-id="795b3-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="795b3-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="795b3-107">Wanneer Microsoft Defender Antivirus een verdacht bestand vindt, kan het voorkomen dat het bestand wordt uitgevoerd terwijl de Microsoft Defender Antivirus [cloudservice wordt opgevraagd.](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="795b3-107">When Microsoft Defender Antivirus finds a suspicious file, it can prevent the file from running while it queries the [Microsoft Defender Antivirus cloud service](cloud-protection-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="795b3-108">De standaardperiode dat het bestand wordt [geblokkeerd,](configure-block-at-first-sight-microsoft-defender-antivirus.md) is 10 seconden.</span><span class="sxs-lookup"><span data-stu-id="795b3-108">The default period that the file will be [blocked](configure-block-at-first-sight-microsoft-defender-antivirus.md) is 10 seconds.</span></span> <span data-ttu-id="795b3-109">U kunt een extra periode opgeven om te wachten voordat het bestand mag worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="795b3-109">You can specify an additional period of time to wait before the file is allowed to run.</span></span> <span data-ttu-id="795b3-110">Dit kan ervoor zorgen dat er voldoende tijd is om een juiste bepaling te ontvangen van de Microsoft Defender Antivirus cloudservice.</span><span class="sxs-lookup"><span data-stu-id="795b3-110">This can help ensure there is enough time to receive a proper determination from the Microsoft Defender Antivirus cloud service.</span></span>

## <a name="prerequisites-to-use-the-extended-cloud-block-timeout"></a><span data-ttu-id="795b3-111">Vereisten voor het gebruik van de time-out voor uitgebreide cloudblokkering</span><span class="sxs-lookup"><span data-stu-id="795b3-111">Prerequisites to use the extended cloud block timeout</span></span>

<span data-ttu-id="795b3-112">[Blok op het eerste gezicht](configure-block-at-first-sight-microsoft-defender-antivirus.md) en de vereisten moeten zijn ingeschakeld voordat u een langere time-outperiode kunt opgeven.</span><span class="sxs-lookup"><span data-stu-id="795b3-112">[Block at first sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) and its prerequisites must be enabled before you can specify an extended timeout period.</span></span>

## <a name="specify-the-extended-timeout-period"></a><span data-ttu-id="795b3-113">De verlengde time-outperiode opgeven</span><span class="sxs-lookup"><span data-stu-id="795b3-113">Specify the extended timeout period</span></span>

<span data-ttu-id="795b3-114">U kunt Groepsbeleid gebruiken om een uitgebreide time-out voor cloudcontroles op te geven.</span><span class="sxs-lookup"><span data-stu-id="795b3-114">You can use Group Policy to specify an extended timeout for cloud checks.</span></span>

1. <span data-ttu-id="795b3-115">Open op de computer groepsbeleidsbeheer de console Groepsbeleidsbeheer, [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik op **Bewerken.**</span><span class="sxs-lookup"><span data-stu-id="795b3-115">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="795b3-116">Ga in **groepsbeleidseditor** naar **Computerconfiguratie** en klik op **Beheersjablonen.**</span><span class="sxs-lookup"><span data-stu-id="795b3-116">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="795b3-117">Vouw de boom uit **Windows onderdelen > Microsoft Defender Antivirus > MpEngine**</span><span class="sxs-lookup"><span data-stu-id="795b3-117">Expand the tree to **Windows components > Microsoft Defender Antivirus > MpEngine**</span></span>

4. <span data-ttu-id="795b3-118">Dubbelklik op **Uitgebreide cloudcontrole configureren** en controleer of de optie is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="795b3-118">Double-click **Configure extended cloud check** and ensure the option is enabled.</span></span> <span data-ttu-id="795b3-119">Geef de extra tijd op om te voorkomen dat het bestand wordt uitgevoerd terwijl u wacht op een cloudbepaling.</span><span class="sxs-lookup"><span data-stu-id="795b3-119">Specify the additional amount of time to prevent the file from running while waiting for a cloud determination.</span></span> <span data-ttu-id="795b3-120">U kunt de extra tijd in seconden opgeven van 1 seconde tot 50 seconden.</span><span class="sxs-lookup"><span data-stu-id="795b3-120">You can specify the additional time, in seconds, from 1 second to 50 seconds.</span></span> <span data-ttu-id="795b3-121">Deze tijd wordt toegevoegd aan de standaard 10 seconden.</span><span class="sxs-lookup"><span data-stu-id="795b3-121">This time will be added to the default 10 seconds.</span></span>

5. <span data-ttu-id="795b3-122">Klik op **OK**.</span><span class="sxs-lookup"><span data-stu-id="795b3-122">Click **OK**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="795b3-123">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="795b3-123">Related topics</span></span>

- [<span data-ttu-id="795b3-124">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="795b3-124">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="795b3-125">Antivirustechnologieën van de volgende generatie gebruiken via door de cloud geleverde beveiliging</span><span class="sxs-lookup"><span data-stu-id="795b3-125">Use next-generation antivirus technologies through cloud-delivered protection</span></span>](cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="795b3-126">Blok configureren op het eerste gezicht</span><span class="sxs-lookup"><span data-stu-id="795b3-126">Configure block at first sight</span></span>](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [<span data-ttu-id="795b3-127">Beveiliging via de cloud inschakelen</span><span class="sxs-lookup"><span data-stu-id="795b3-127">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)