---
title: Prestatieproblemen oplossen voor Microsoft Defender ATP voor Mac
description: Problemen met de prestaties oplossen in Microsoft Defender ATP voor Mac.
keywords: microsoft, defender, atp, mac, performance
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: dbd82bae86ac4181497ecc87bc74181f7a502e15
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51057373"
---
# <a name="troubleshoot-performance-issues-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="3875a-104">Prestatieproblemen oplossen voor Microsoft Defender voor Eindpunt voor Mac</span><span class="sxs-lookup"><span data-stu-id="3875a-104">Troubleshoot performance issues for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="3875a-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="3875a-105">**Applies to:**</span></span>

- [<span data-ttu-id="3875a-106">Microsoft Defender voor Eindpunt voor Mac</span><span class="sxs-lookup"><span data-stu-id="3875a-106">Microsoft Defender for Endpoint for Mac</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="3875a-107">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="3875a-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="3875a-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3875a-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="3875a-109">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="3875a-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3875a-110">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="3875a-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="3875a-111">Dit onderwerp bevat enkele algemene stappen die kunnen worden gebruikt om prestatieproblemen met betrekking tot Microsoft Defender voor Eindpunt voor Mac te beperken.</span><span class="sxs-lookup"><span data-stu-id="3875a-111">This topic provides some general steps that can be used to narrow down performance issues related to Microsoft Defender for Endpoint for Mac.</span></span>

<span data-ttu-id="3875a-112">Realtimebeveiliging (RTP) is een functie van Microsoft Defender voor Endpoint voor Mac waarmee uw apparaat continu wordt bewaakt en beschermd tegen bedreigingen.</span><span class="sxs-lookup"><span data-stu-id="3875a-112">Real-time protection (RTP) is a feature of Microsoft Defender for Endpoint for Mac that continuously monitors and protects your device against threats.</span></span> <span data-ttu-id="3875a-113">Het bestaat uit bestands- en procescontrole en andere heuristieken.</span><span class="sxs-lookup"><span data-stu-id="3875a-113">It consists of file and process monitoring and other heuristics.</span></span>

<span data-ttu-id="3875a-114">Afhankelijk van de toepassingen die u gebruikt en de kenmerken van uw apparaat, kunt u suboptimale prestaties ervaren bij het uitvoeren van Microsoft Defender voor Eindpunt voor Mac.</span><span class="sxs-lookup"><span data-stu-id="3875a-114">Depending on the applications that you are running and your device characteristics, you may experience suboptimal performance when running Microsoft Defender for Endpoint for Mac.</span></span> <span data-ttu-id="3875a-115">Met name toepassingen of systeemprocessen die over een korte periode toegang hebben tot veel resources, kunnen leiden tot prestatieproblemen in Microsoft Defender voor Eindpunt voor Mac.</span><span class="sxs-lookup"><span data-stu-id="3875a-115">In particular, applications or system processes that access many resources over a short timespan can lead to performance issues in Microsoft Defender for Endpoint for Mac.</span></span>

<span data-ttu-id="3875a-116">De volgende stappen kunnen worden gebruikt om deze problemen op te lossen en te beperken:</span><span class="sxs-lookup"><span data-stu-id="3875a-116">The following steps can be used to troubleshoot and mitigate these issues:</span></span>

1. <span data-ttu-id="3875a-117">Schakel realtimebeveiliging uit met behulp van een van de volgende methoden en kijk of de prestaties verbeteren.</span><span class="sxs-lookup"><span data-stu-id="3875a-117">Disable real-time protection using one of the following methods and observe whether the performance improves.</span></span> <span data-ttu-id="3875a-118">Met deze methode kunt u bepalen of Microsoft Defender voor Eindpunt voor Mac bijdraagt aan de prestatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="3875a-118">This approach helps narrow down whether Microsoft Defender for Endpoint for Mac is contributing to the performance issues.</span></span>

    <span data-ttu-id="3875a-119">Als uw apparaat niet wordt beheerd door uw organisatie, kan realtimebeveiliging worden uitgeschakeld met behulp van een van de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="3875a-119">If your device is not managed by your organization, real-time protection can be disabled using one of the following options:</span></span>

    - <span data-ttu-id="3875a-120">Vanuit de gebruikersinterface.</span><span class="sxs-lookup"><span data-stu-id="3875a-120">From the user interface.</span></span> <span data-ttu-id="3875a-121">Open Microsoft Defender voor Eindpunt voor Mac en ga naar **Instellingen beheren.**</span><span class="sxs-lookup"><span data-stu-id="3875a-121">Open Microsoft Defender for Endpoint for Mac and navigate to **Manage settings**.</span></span>

      ![Schermopname van realtimebeveiliging beheren](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-36-rtp)

    - <span data-ttu-id="3875a-123">Vanuit de Terminal.</span><span class="sxs-lookup"><span data-stu-id="3875a-123">From the Terminal.</span></span> <span data-ttu-id="3875a-124">Voor beveiligingsdoeleinden is voor deze bewerking hoogte vereist.</span><span class="sxs-lookup"><span data-stu-id="3875a-124">For security purposes, this operation requires elevation.</span></span>

      ```bash
      mdatp config real-time-protection --value disabled
      ```

    <span data-ttu-id="3875a-125">Als uw apparaat wordt beheerd door uw organisatie, kan realtimebeveiliging worden uitgeschakeld door uw beheerder met behulp van de instructies in Voorkeuren instellen voor [Microsoft Defender voor Eindpunt voor Mac.](mac-preferences.md)</span><span class="sxs-lookup"><span data-stu-id="3875a-125">If your device is managed by your organization, real-time protection can be disabled by your administrator using the instructions in [Set preferences for Microsoft Defender for Endpoint for Mac](mac-preferences.md).</span></span>

2. <span data-ttu-id="3875a-126">Open Finder en navigeer naar **Applications**  >  **Utilities.**</span><span class="sxs-lookup"><span data-stu-id="3875a-126">Open Finder and navigate to **Applications** > **Utilities**.</span></span> <span data-ttu-id="3875a-127">Open **Activiteitsmonitor** en analyseer welke toepassingen de resources op uw systeem gebruiken.</span><span class="sxs-lookup"><span data-stu-id="3875a-127">Open **Activity Monitor** and analyze which applications are using the resources on your system.</span></span> <span data-ttu-id="3875a-128">Voorbeelden hiervan zijn software-updaters en compilers.</span><span class="sxs-lookup"><span data-stu-id="3875a-128">Typical examples include software updaters and compilers.</span></span>

3. <span data-ttu-id="3875a-129">Configureer Microsoft Defender voor Eindpunt voor Mac met uitsluitingen voor de processen of schijflocaties die bijdragen aan de prestatieproblemen en realtime beveiliging opnieuw inschakelen.</span><span class="sxs-lookup"><span data-stu-id="3875a-129">Configure Microsoft Defender for Endpoint for Mac with exclusions for the processes or disk locations that contribute to the performance issues and re-enable real-time protection.</span></span>

    <span data-ttu-id="3875a-130">Zie [Uitsluitingen configureren en valideren voor Microsoft Defender voor Eindpunt voor Mac](mac-exclusions.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="3875a-130">See [Configure and validate exclusions for Microsoft Defender for Endpoint for Mac](mac-exclusions.md) for details.</span></span>
