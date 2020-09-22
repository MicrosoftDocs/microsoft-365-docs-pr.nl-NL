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
description: Integratie van Office 365 Advanced Threat Protection met Microsoft Defender Advanced Threat Protection voor meer gedetailleerde informatie over risicobeheer.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0906b8b44922084a65999dd9ab10a09c827605c2
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201969"
---
# <a name="integrate-office-365-advanced-threat-protection-with-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="77b3e-103">Office 365 Advanced Threat Protection integreren met Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="77b3e-103">Integrate Office 365 Advanced Threat Protection with Microsoft Defender Advanced Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="77b3e-104">[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) (Office 365 ATP) kan worden geconfigureerd voor gebruik met [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection) (Microsoft Defender ATP).</span><span class="sxs-lookup"><span data-stu-id="77b3e-104">[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) (Office 365 ATP) can be configured to work with [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection) (Microsoft Defender ATP).</span></span>

<span data-ttu-id="77b3e-105">Het integreren van Office 365-ATP met Microsoft Defender ATP kan de team monitor van uw beveiliging en de werking van de gebruikers snel uitvoeren als de apparaten van de gebruikers risico lopen.</span><span class="sxs-lookup"><span data-stu-id="77b3e-105">Integrating Office 365 ATP with Microsoft Defender ATP can help your security operations team monitor and take action quickly if users' devices are at risk.</span></span> <span data-ttu-id="77b3e-106">Wanneer de integratie is ingeschakeld, kunnen uw beveiligingsteam bijvoorbeeld de apparaten zien waarop het gedetecteerde e-mailbericht mogelijk invloed heeft en van het aantal recente meldingen voor deze apparaten in Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="77b3e-106">For example, once integration is enabled, your security operations team will be able to see the devices that are potentially affected by a detected email message, as well as how many recent alerts those devices have in Microsoft Defender ATP.</span></span> 

<span data-ttu-id="77b3e-107">In de volgende afbeelding wordt getoond waarop op het tabblad **apparaten** de integratie met Microsoft Defender ATP is ingeschakeld:</span><span class="sxs-lookup"><span data-stu-id="77b3e-107">The following image depicts what the **Devices** tab looks like have Microsoft Defender ATP integration enabled:</span></span>
  
![Wanneer Microsoft Defender ATP is ingeschakeld, kunt u een lijst met apparaten met waarschuwingen weergeven.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
<span data-ttu-id="77b3e-109">In dit voorbeeld ziet u dat de geadresseerden van het gedetecteerde e-mailbericht vier apparaten hebben en dat er een waarschuwing is.</span><span class="sxs-lookup"><span data-stu-id="77b3e-109">In this example, you can see that the recipients of the detected email message have four devices and one has an alert.</span></span> <span data-ttu-id="77b3e-110">Als u op de koppeling voor een apparaat klikt, wordt de pagina geopend in het Microsoft Defender-Beveiligingscentrum [https://securitycenter.windows.com](https://securitycenter.windows.com) .</span><span class="sxs-lookup"><span data-stu-id="77b3e-110">Clicking the link for a device opens its page in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

> [!TIP]
> <span data-ttu-id="77b3e-111">Meer **[informatie over het Microsoft Defender-Beveiligingscentrum](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (ook wel Microsoft Defender ATP Portal genoemd).</span><span class="sxs-lookup"><span data-stu-id="77b3e-111">**[Learn more about the Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (also referred to as the Microsoft Defender ATP portal.)</span></span>
  
## <a name="requirements"></a><span data-ttu-id="77b3e-112">Vereisten</span><span class="sxs-lookup"><span data-stu-id="77b3e-112">Requirements</span></span>

- <span data-ttu-id="77b3e-113">Uw organisatie moet Office 365 ATP, abonnement 2 (of Office 365 E5) en Microsoft Defender ATP hebben.</span><span class="sxs-lookup"><span data-stu-id="77b3e-113">Your organization must have Office 365 ATP Plan 2 (or Office 365 E5) and Microsoft Defender ATP.</span></span>
    
- <span data-ttu-id="77b3e-114">U moet een hoofdbeheerder zijn of de rol van beveiligingsbeheerder (zoals beveiligingsbeheerder) hebben die is toegewezen aan het [beveiligings &amp; conformiteitscentrum](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="77b3e-114">You must be a global administrator or have a security administrator role (such as Security Administrator) assigned in the [Security &amp; Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="77b3e-115">(Zie [machtigingen in het Security &amp; compliance Center](permissions-in-the-security-and-compliance-center.md))</span><span class="sxs-lookup"><span data-stu-id="77b3e-115">(See [Permissions in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>
    
- <span data-ttu-id="77b3e-116">U moet in de beveiligings & nalevings centrum en het Microsoft Defender-Beveiligingscentrum toegang hebben tot zowel de [Verkenner (of realtime detectie)](threat-explorer.md) .</span><span class="sxs-lookup"><span data-stu-id="77b3e-116">You must have access to both [Explorer (or real-time detections)](threat-explorer.md) in the Security & Compliance Center and the Microsoft Defender Security Center.</span></span>
    
## <a name="to-integrate-office-365-atp-with-microsoft-defender-atp"></a><span data-ttu-id="77b3e-117">Office 365 ATP integreren met Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="77b3e-117">To integrate Office 365 ATP with Microsoft Defender ATP</span></span>

<span data-ttu-id="77b3e-118">Het integreren van Office 365-ATP met Microsoft Defender ATP wordt ingesteld met behulp van het beveiligings & nalevings centrum en het Microsoft Defender-Beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="77b3e-118">Integrating Office 365 ATP with Microsoft Defender ATP is set up by using both the Security & Compliance Center AND the Microsoft Defender Security Center.</span></span>
  
1. <span data-ttu-id="77b3e-119">Ga als globale beheerder of een beveiligingsbeheerder naar [https://protection.office.com](https://protection.office.com) en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="77b3e-119">As a global administrator or a security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="77b3e-120">(U gaat nu naar het Beveiligingscentrum van Office 365 & nalevings centrum.)</span><span class="sxs-lookup"><span data-stu-id="77b3e-120">(This takes you to the Office 365 Security & Compliance Center.)</span></span>
    
2. <span data-ttu-id="77b3e-121">Kies in het navigatiedeelvenster de optie **Threat Management**  >  **Explorer**.</span><span class="sxs-lookup"><span data-stu-id="77b3e-121">In the navigation pane, choose **Threat management** > **Explorer**.</span></span><br><span data-ttu-id="77b3e-122">![Verkenner in het menu Threat Management](../../media/ThreatMgmt-Explorer-nav.png)</span><span class="sxs-lookup"><span data-stu-id="77b3e-122">![Explorer in Threat Management menu](../../media/ThreatMgmt-Explorer-nav.png)</span></span><br>
    
3. <span data-ttu-id="77b3e-123">Kies in de rechterbovenhoek van het scherm **WDATP instellingen**.</span><span class="sxs-lookup"><span data-stu-id="77b3e-123">In the upper right corner of the screen, choose **WDATP Settings**.</span></span>
    
4. <span data-ttu-id="77b3e-124">Schakel in het dialoogvenster verbinding met Microsoft Defender ATP de optie **verbinding maken met Windows ATP**in.</span><span class="sxs-lookup"><span data-stu-id="77b3e-124">In the Microsoft Defender ATP connection dialog box, turn on **Connect to Windows ATP**.</span></span><br><span data-ttu-id="77b3e-125">![Microsoft Defender ATP-verbinding](../../media/Explorer-WDATPConnection-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="77b3e-125">![Microsoft Defender ATP connection](../../media/Explorer-WDATPConnection-dialog.png)</span></span><br>
    
5. <span data-ttu-id="77b3e-126">Ga naar het Microsoft Defender-Beveiligingscentrum ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).</span><span class="sxs-lookup"><span data-stu-id="77b3e-126">Go to the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

6. <span data-ttu-id="77b3e-127">Kies in de navigatiebalk de optie **instellingen**.</span><span class="sxs-lookup"><span data-stu-id="77b3e-127">In the navigation bar, choose **Settings**.</span></span> <span data-ttu-id="77b3e-128">Kies vervolgens onder **Algemeen** **geavanceerde functies**.</span><span class="sxs-lookup"><span data-stu-id="77b3e-128">Then, under **General**, choose **Advanced features**.</span></span>

7. <span data-ttu-id="77b3e-129">Schuif omlaag naar **Office 365 Threat Intelligence-verbinding**en zet de verbinding aan.</span><span class="sxs-lookup"><span data-stu-id="77b3e-129">Scroll down to **Office 365 Threat Intelligence connection**, and turn the connection on.</span></span><br/><span data-ttu-id="77b3e-130">![Office 365 Threat Intelligence-verbinding](../../media/mdatp-oatptoggle.png)</span><span class="sxs-lookup"><span data-stu-id="77b3e-130">![Office 365 threat intelligence connection](../../media/mdatp-oatptoggle.png)</span></span><br>

## <a name="related-articles"></a><span data-ttu-id="77b3e-131">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="77b3e-131">Related articles</span></span>

[<span data-ttu-id="77b3e-132">Oplossing voor onderzoek en antwoord van bedreigingen in Office 365</span><span class="sxs-lookup"><span data-stu-id="77b3e-132">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)
  
[<span data-ttu-id="77b3e-133">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="77b3e-133">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="77b3e-134">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="77b3e-134">Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection)
