---
title: De beperkte periodieke scanfunctie voor Microsoft Defender Antivirus inschakelen
description: Met beperkt periodiek scannen kunt u Naast uw andere geïnstalleerde AV-providers ook Microsoft Defender Antivirus gebruiken
keywords: lps, limited, periodic, scan, scanning, compatibility, 3rd party, other av, disable
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 64b65363ff53773f73cbbdc33b05a0a1beaf7f92
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690600"
---
# <a name="use-limited-periodic-scanning-in-microsoft-defender-antivirus"></a><span data-ttu-id="41377-104">Beperkt periodiek scannen gebruiken in Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="41377-104">Use limited periodic scanning in Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="41377-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="41377-105">**Applies to:**</span></span>

- [<span data-ttu-id="41377-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="41377-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="41377-107">Beperkt periodiek scannen is een speciaal type bedreigingsdetectie en -herstel dat kan worden ingeschakeld wanneer u een ander antivirusproduct hebt geïnstalleerd op een Windows 10-apparaat.</span><span class="sxs-lookup"><span data-stu-id="41377-107">Limited periodic scanning is a special type of threat detection and remediation that can be enabled when you have installed another antivirus product on a Windows 10 device.</span></span>

<span data-ttu-id="41377-108">Deze functie kan alleen in bepaalde situaties worden ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="41377-108">It can only be enabled in certain situations.</span></span> <span data-ttu-id="41377-109">Zie Microsoft Defender Antivirus compatibility voor meer informatie over beperkt periodiek scannen en hoe Microsoft Defender Antivirus werkt met andere [antivirusproducten.](microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="41377-109">For more information about limited periodic scanning and how Microsoft Defender Antivirus works with other antivirus products, see [Microsoft Defender Antivirus compatibility](microsoft-defender-antivirus-compatibility.md).</span></span>

<span data-ttu-id="41377-110">**Microsoft raadt het gebruik van deze functie niet aan in bedrijfsomgevingen. Dit is een functie die voornamelijk bedoeld is voor consumenten.**</span><span class="sxs-lookup"><span data-stu-id="41377-110">**Microsoft does not recommend using this feature in enterprise environments. This is a feature primarily intended for consumers.**</span></span> <span data-ttu-id="41377-111">Deze functie gebruikt slechts een beperkte subset van de Microsoft Defender Antivirus-mogelijkheden om malware te detecteren en kan de meeste malware en mogelijk ongewenste software niet detecteren.</span><span class="sxs-lookup"><span data-stu-id="41377-111">This feature only uses a limited subset of the Microsoft Defender Antivirus capabilities to detect malware, and will not be able to detect most malware and potentially unwanted software.</span></span> <span data-ttu-id="41377-112">Daarnaast zijn de beheer- en rapportagemogelijkheden beperkt.</span><span class="sxs-lookup"><span data-stu-id="41377-112">Also, management and reporting capabilities will be limited.</span></span> <span data-ttu-id="41377-113">Microsoft raadt ondernemingen aan hun primaire antivirusoplossing te kiezen en deze uitsluitend te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="41377-113">Microsoft recommends enterprises choose their primary antivirus solution and use it exclusively.</span></span>

## <a name="how-to-enable-limited-periodic-scanning"></a><span data-ttu-id="41377-114">Beperkt periodiek scannen inschakelen</span><span class="sxs-lookup"><span data-stu-id="41377-114">How to enable limited periodic scanning</span></span>

<span data-ttu-id="41377-115">Standaard wordt Microsoft Defender Antivirus ingeschakeld op een Windows 10-apparaat als er geen ander antivirusproduct is geïnstalleerd of als het andere product verouderd, verlopen of niet correct werkt.</span><span class="sxs-lookup"><span data-stu-id="41377-115">By default, Microsoft Defender Antivirus will enable itself on a Windows 10 device if there is no other antivirus product installed, or if the other product is out-of-date, expired, or not working correctly.</span></span>

<span data-ttu-id="41377-116">Als Microsoft Defender Antivirus is ingeschakeld, worden de gebruikelijke opties weergegeven om het te configureren op dat apparaat:</span><span class="sxs-lookup"><span data-stu-id="41377-116">If Microsoft Defender Antivirus is enabled, the usual options will appear to configure it on that device:</span></span>

![Windows Security-app met Microsoft Defender AV-opties, inclusief scanopties, instellingen en bijwerkopties](images/vtp-wdav.png)

<span data-ttu-id="41377-118">Als een ander antivirusproduct is geïnstalleerd en goed werkt, wordt Microsoft Defender Antivirus zelf uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="41377-118">If another antivirus product is installed and working correctly, Microsoft Defender Antivirus will disable itself.</span></span> <span data-ttu-id="41377-119">De Windows Security-app wijzigt de sectie **Virus & bedreigingsbeveiliging** om de status van het AV-product weer te geven en geeft een koppeling naar de configuratieopties van het product.</span><span class="sxs-lookup"><span data-stu-id="41377-119">The Windows Security app will change the **Virus & threat protection** section to show status about the AV product, and provide a link to the product's configuration options.</span></span>

<span data-ttu-id="41377-120">Onder av-producten van derden wordt een nieuwe koppeling weergegeven als **Microsoft Defender Antivirus-opties.**</span><span class="sxs-lookup"><span data-stu-id="41377-120">Underneath any third party AV products, a new link will appear as **Microsoft Defender Antivirus options**.</span></span> <span data-ttu-id="41377-121">Als u op deze koppeling klikt, wordt de schakelknop die beperkt periodiek scannen in staat stelt, uitvlage.</span><span class="sxs-lookup"><span data-stu-id="41377-121">Clicking this link will expand to show the toggle that enables limited periodic scanning.</span></span> <span data-ttu-id="41377-122">Houd er rekening mee dat de beperkte periodieke optie een schakeloptie is om periodiek scannen in of uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="41377-122">Note that the limited periodic option is a toggle to enable or disable periodic scanning.</span></span> 

<span data-ttu-id="41377-123">Als u de overstap naar **Aan** schuift, worden de standaard microsoft Defender AV-opties onder het AV-product van derden weer te geven.</span><span class="sxs-lookup"><span data-stu-id="41377-123">Sliding the switch to **On** will show the standard Microsoft Defender AV options underneath the third party AV product.</span></span> <span data-ttu-id="41377-124">De beperkte optie voor periodiek scannen wordt onder aan de pagina weergegeven.</span><span class="sxs-lookup"><span data-stu-id="41377-124">The limited periodic scanning option will appear at the bottom of the page.</span></span>

## <a name="related-articles"></a><span data-ttu-id="41377-125">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="41377-125">Related articles</span></span>

- [<span data-ttu-id="41377-126">Gedrags-, heuristische en realtimebeveiliging configureren</span><span class="sxs-lookup"><span data-stu-id="41377-126">Configure behavioral, heuristic, and real-time protection</span></span>](configure-protection-features-microsoft-defender-antivirus.md)
- [<span data-ttu-id="41377-127">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="41377-127">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)