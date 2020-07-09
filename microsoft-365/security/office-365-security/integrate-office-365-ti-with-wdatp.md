---
title: Office 365 ATP integreren met Microsoft Defender ATP
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 07/08/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 414fa693-d7b7-4a1d-a387-ebc3b6a52889
ms.collection:
- M365-security-compliance
description: Integreer Office 365 Advanced Threat Protection met Microsoft Defender Advanced Threat Protection voor meer gedetailleerde informatie over bedreigingsbeheer.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bfb87edd24a22033b3771ba0fd3c4f1afbbc988e
ms.sourcegitcommit: 41bc923bb31598cea8f02923792c1cd786e39616
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086706"
---
# <a name="integrate-office-365-advanced-threat-protection-with-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="f7f0e-103">Office 365 Advanced Threat Protection integreren met geavanceerde bedreigingsbeveiliging van Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f7f0e-103">Integrate Office 365 Advanced Threat Protection with Microsoft Defender Advanced Threat Protection</span></span>

<span data-ttu-id="f7f0e-104">[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) (Office 365 ATP) kan worden geconfigureerd om te werken met [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection) (Microsoft Defender ATP).</span><span class="sxs-lookup"><span data-stu-id="f7f0e-104">[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) (Office 365 ATP) can be configured to work with [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection) (Microsoft Defender ATP).</span></span>

<span data-ttu-id="f7f0e-105">Als u Office 365 ATP integreert met Microsoft Defender ATP, kan uw beveiligingsteam snel kunnen controleren en actie ondernemen als de apparaten van gebruikers gevaar lopen.</span><span class="sxs-lookup"><span data-stu-id="f7f0e-105">Integrating Office 365 ATP with Microsoft Defender ATP can help your security operations team monitor and take action quickly if users' devices are at risk.</span></span> <span data-ttu-id="f7f0e-106">Zodra integratie is ingeschakeld, kan uw beveiligingsteam bijvoorbeeld de apparaten zien die mogelijk worden beïnvloed door een gedetecteerd e-mailbericht en hoeveel recente waarschuwingen deze apparaten hebben in Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="f7f0e-106">For example, once integration is enabled, your security operations team will be able to see the devices that are potentially affected by a detected email message, as well as how many recent alerts those devices have in Microsoft Defender ATP.</span></span> 

<span data-ttu-id="f7f0e-107">In de volgende afbeelding wordt weergegeven hoe het tabblad **Apparaten** eruitziet als Microsoft Defender ATP-integratie is ingeschakeld:</span><span class="sxs-lookup"><span data-stu-id="f7f0e-107">The following image depicts what the **Devices** tab looks like have Microsoft Defender ATP integration enabled:</span></span>
  
![Wanneer Microsoft Defender ATP is ingeschakeld, ziet u een lijst met apparaten met waarschuwingen.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
<span data-ttu-id="f7f0e-109">In dit voorbeeld u zien dat de ontvangers van het gedetecteerde e-mailbericht vier apparaten hebben en één een waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="f7f0e-109">In this example, you can see that the recipients of the detected email message have four devices and one has an alert.</span></span> <span data-ttu-id="f7f0e-110">Als u op de koppeling voor een apparaat klikt, wordt de pagina geopend in het Microsoft Defender Security Center ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).</span><span class="sxs-lookup"><span data-stu-id="f7f0e-110">Clicking the link for a device opens its page in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

> [!TIP]
> <span data-ttu-id="f7f0e-111">**[Meer informatie over het Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (ook wel de Microsoft Defender ATP-portal genoemd).)</span><span class="sxs-lookup"><span data-stu-id="f7f0e-111">**[Learn more about the Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (also referred to as the Microsoft Defender ATP portal.)</span></span>
  
## <a name="requirements"></a><span data-ttu-id="f7f0e-112">Vereisten</span><span class="sxs-lookup"><span data-stu-id="f7f0e-112">Requirements</span></span>

- <span data-ttu-id="f7f0e-113">Uw organisatie moet beschikken over Office 365 ATP Plan 2 (of Office 365 E5) en Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="f7f0e-113">Your organization must have Office 365 ATP Plan 2 (or Office 365 E5) and Microsoft Defender ATP.</span></span>
    
- <span data-ttu-id="f7f0e-114">U moet een globale beheerder zijn of een beveiligingsbeheerdersrol (zoals beveiligingsbeheerder) hebben toegewezen in het [Security &amp; Compliance Center](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="f7f0e-114">You must be a global administrator or have a security administrator role (such as Security Administrator) assigned in the [Security &amp; Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="f7f0e-115">(Zie [machtigingen in het Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md))</span><span class="sxs-lookup"><span data-stu-id="f7f0e-115">(See [Permissions in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>
    
- <span data-ttu-id="f7f0e-116">U moet toegang hebben tot zowel [Explorer (of real-time detecties)](threat-explorer.md) in het Security & Compliance Center als het Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="f7f0e-116">You must have access to both [Explorer (or real-time detections)](threat-explorer.md) in the Security & Compliance Center and the Microsoft Defender Security Center.</span></span>
    
## <a name="to-integrate-office-365-atp-with-microsoft-defender-atp"></a><span data-ttu-id="f7f0e-117">Office 365 ATP integreren met Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="f7f0e-117">To integrate Office 365 ATP with Microsoft Defender ATP</span></span>

<span data-ttu-id="f7f0e-118">De integratie van Office 365 ATP met Microsoft Defender ATP is opgezet met behulp van zowel het Security & Compliance Center als het Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="f7f0e-118">Integrating Office 365 ATP with Microsoft Defender ATP is set up by using both the Security & Compliance Center AND the Microsoft Defender Security Center.</span></span>
  
1. <span data-ttu-id="f7f0e-119">Ga als globale beheerder of beveiligingsbeheerder naar [https://protection.office.com](https://protection.office.com) en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="f7f0e-119">As a global administrator or a security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="f7f0e-120">(Hiermee gaat u naar het Office 365 Security & Compliance Center.)</span><span class="sxs-lookup"><span data-stu-id="f7f0e-120">(This takes you to the Office 365 Security & Compliance Center.)</span></span>
    
2. <span data-ttu-id="f7f0e-121">Kies in het navigatiedeelvenster **Bedreigingsbeheerverkenner**  >  **Explorer**.</span><span class="sxs-lookup"><span data-stu-id="f7f0e-121">In the navigation pane, choose **Threat management** > **Explorer**.</span></span><br><span data-ttu-id="f7f0e-122">![Explorer in het menu Bedreigingsbeheer](../../media/ThreatMgmt-Explorer-nav.png)</span><span class="sxs-lookup"><span data-stu-id="f7f0e-122">![Explorer in Threat Management menu](../../media/ThreatMgmt-Explorer-nav.png)</span></span><br>
    
3. <span data-ttu-id="f7f0e-123">Kies in de rechterbovenhoek van het scherm **WDATP-instellingen.**</span><span class="sxs-lookup"><span data-stu-id="f7f0e-123">In the upper right corner of the screen, choose **WDATP Settings**.</span></span>
    
4. <span data-ttu-id="f7f0e-124">Schakel verbinding **maken met Windows ATP**in het dialoogvenster Microsoft Defender ATP in .</span><span class="sxs-lookup"><span data-stu-id="f7f0e-124">In the Microsoft Defender ATP connection dialog box, turn on **Connect to Windows ATP**.</span></span><br><span data-ttu-id="f7f0e-125">![Microsoft Defender ATP-verbinding](../../media/Explorer-WDATPConnection-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="f7f0e-125">![Microsoft Defender ATP connection](../../media/Explorer-WDATPConnection-dialog.png)</span></span><br>
    
5. <span data-ttu-id="f7f0e-126">Ga naar het Microsoft Defender Security Center ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).</span><span class="sxs-lookup"><span data-stu-id="f7f0e-126">Go to the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

6. <span data-ttu-id="f7f0e-127">Kies **Instellingen op**de navigatiebalk .</span><span class="sxs-lookup"><span data-stu-id="f7f0e-127">In the navigation bar, choose **Settings**.</span></span> <span data-ttu-id="f7f0e-128">Kies vervolgens onder **Algemeen** **geavanceerde functies**.</span><span class="sxs-lookup"><span data-stu-id="f7f0e-128">Then, under **General**, choose **Advanced features**.</span></span>

7. <span data-ttu-id="f7f0e-129">Schuif omlaag naar de Verbinding Met De Informatie van de Bedreiging van **Office 365**en schakel de verbinding in.</span><span class="sxs-lookup"><span data-stu-id="f7f0e-129">Scroll down to **Office 365 Threat Intelligence connection**, and turn the connection on.</span></span><br/><span data-ttu-id="f7f0e-130">![Verbinding met de informatie over bedreigingen van Office 365](../../media/mdatp-oatptoggle.png)</span><span class="sxs-lookup"><span data-stu-id="f7f0e-130">![Office 365 threat intelligence connection](../../media/mdatp-oatptoggle.png)</span></span><br>

## <a name="related-articles"></a><span data-ttu-id="f7f0e-131">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="f7f0e-131">Related articles</span></span>

[<span data-ttu-id="f7f0e-132">Mogelijkheden voor bedreigingsonderzoek en -reactie in Office 365</span><span class="sxs-lookup"><span data-stu-id="f7f0e-132">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)
  
[<span data-ttu-id="f7f0e-133">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="f7f0e-133">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="f7f0e-134">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="f7f0e-134">Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection)
