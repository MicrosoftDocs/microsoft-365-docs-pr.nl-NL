---
title: Office 365 Advanced Threat Protection integreren met Microsoft Defender Advanced Threat Protection
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 04/13/2020
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
ms.openlocfilehash: a2634a70bdbdd21efe2c59721e5532500eb4e4cc
ms.sourcegitcommit: 4c6af6530b4997055b8e60bf532e75cbc72fb6c5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/14/2020
ms.locfileid: "43284222"
---
# <a name="integrate-office-365-advanced-threat-protection-with-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="dfff6-103">Office 365 Advanced Threat Protection integreren met Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="dfff6-103">Integrate Office 365 Advanced Threat Protection with Microsoft Defender Advanced Threat Protection</span></span>

<span data-ttu-id="dfff6-104">Als u deel uitmaakt van het beveiligingsteam van uw organisatie, u [Office 365 Advanced Threat Protection](office-365-atp.md) en gerelateerde onderzoeks- en reactiefuncties integreren met Microsoft Defender Advanced Threat [Protection.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="dfff6-104">If you are part of your organization's security team, you can integrate [Office 365 Advanced Threat Protection](office-365-atp.md) and related investigation and response features with [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection).</span></span> <span data-ttu-id="dfff6-105">Dit kan u helpen snel te begrijpen of de machines van gebruikers risico lopen wanneer u bedreigingen in Office 365 onderzoekt.</span><span class="sxs-lookup"><span data-stu-id="dfff6-105">This can help you quickly understand if users' machines are at risk when you are investigating threats in Office 365.</span></span> <span data-ttu-id="dfff6-106">Zodra de integratie is ingeschakeld, u bijvoorbeeld een lijst zien met machines die worden gebruikt door de ontvangers van een gedetecteerd e-mailbericht, evenals hoeveel recente waarschuwingen deze machines hebben in Microsoft Defender Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="dfff6-106">For example, once integration is enabled, you will be able to see a list of machines that are used by the recipients of a detected email message, as well as how many recent alerts those machines have in Microsoft Defender Advanced Threat Protection.</span></span>
  
<span data-ttu-id="dfff6-107">In de volgende afbeelding ziet u het tabblad **Apparaten** dat u ziet wanneer de ATP-integratie van Microsoft Defender is ingeschakeld:</span><span class="sxs-lookup"><span data-stu-id="dfff6-107">The following image shows the **Devices** tab that you'll see when have Microsoft Defender ATP integration enabled:</span></span>
  
![Wanneer Microsoft Defender ATP is ingeschakeld, u een lijst met apparaten met waarschuwingen zien.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
<span data-ttu-id="dfff6-109">In dit voorbeeld u zien dat de ontvangers van het e-mailbericht vier apparaten hebben en één een waarschuwing heeft.</span><span class="sxs-lookup"><span data-stu-id="dfff6-109">In this example, you can see that the recipients of the email message have four devices and one has an alert.</span></span> <span data-ttu-id="dfff6-110">Als u op de koppeling voor een apparaat klikt, wordt de pagina geopend in het Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="dfff6-110">Clicking the link for a device opens its page in the Microsoft Defender Security Center.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="dfff6-111">Vereisten</span><span class="sxs-lookup"><span data-stu-id="dfff6-111">Requirements</span></span>

- <span data-ttu-id="dfff6-112">Uw organisatie moet beschikken over Office 365 ATP Plan 2 (of Office 365 E5) en Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="dfff6-112">Your organization must have Office 365 ATP Plan 2 (or Office 365 E5) and Microsoft Defender ATP.</span></span>
    
- <span data-ttu-id="dfff6-113">U moet een globale beheerder van Office 365 zijn of een beveiligingsbeheerderfunctie (zoals beveiligingsbeheerder) toegewezen hebben in het [Security &amp; Compliance Center.](https://protection.office.com)</span><span class="sxs-lookup"><span data-stu-id="dfff6-113">You must be an Office 365 Global Administrator or have a security administrator role (such as Security Administrator) assigned in the [Security &amp; Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="dfff6-114">(Zie [Machtigingen in het Office &amp; 365 Security Compliance Center)](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="dfff6-114">(See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>
    
- <span data-ttu-id="dfff6-115">U moet toegang hebben tot zowel [Explorer (of real-time detecties)](threat-explorer.md) in het Security & Compliance Center en het Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="dfff6-115">You must have access to both [Explorer (or real-time detections)](threat-explorer.md) in the Security & Compliance Center and the Microsoft Defender Security Center.</span></span>
    
## <a name="to-integrate-office-365-atp-with-microsoft-defender-atp"></a><span data-ttu-id="dfff6-116">Office 365 ATP integreren met Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="dfff6-116">To integrate Office 365 ATP with Microsoft Defender ATP</span></span>

<span data-ttu-id="dfff6-117">De integratie van Office 365 ATP met Microsoft Defender ATP is ingesteld met zowel het Office 365 Security & Compliance Center als het Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="dfff6-117">Integrating Office 365 ATP with Microsoft Defender ATP is set up by using both the Office 365 Security & Compliance Center AND the Microsoft Defender Security Center.</span></span>
  
1. <span data-ttu-id="dfff6-118">Ga als globale office 365-beheerder of [https://protection.office.com](https://protection.office.com) beveiligingsbeheerder naar en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="dfff6-118">As an Office 365 global administrator or a security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span>
    
2. <span data-ttu-id="dfff6-119">Kies **Threat management** \> **Explorer**.</span><span class="sxs-lookup"><span data-stu-id="dfff6-119">Choose **Threat management** \> **Explorer**.</span></span><br><span data-ttu-id="dfff6-120">![Explorer in het menu Bedreigingsbeheer](../../media/ThreatMgmt-Explorer-nav.png)</span><span class="sxs-lookup"><span data-stu-id="dfff6-120">![Explorer in Threat Management menu](../../media/ThreatMgmt-Explorer-nav.png)</span></span><br>
    
3. <span data-ttu-id="dfff6-121">Kies **WDATP-instellingen**in de rechterbovenhoek van het scherm .</span><span class="sxs-lookup"><span data-stu-id="dfff6-121">In the upper right corner of the screen, choose **WDATP Settings**.</span></span>
    
4. <span data-ttu-id="dfff6-122">Schakel in het dialoogvenster Microsoft Defender ATP-verbinding **Verbinding maken met Windows ATP**in.</span><span class="sxs-lookup"><span data-stu-id="dfff6-122">In the Microsoft Defender ATP connection dialog box, turn on **Connect to Windows ATP**.</span></span><br><span data-ttu-id="dfff6-123">![Microsoft Defender ATP-verbinding](../../media/Explorer-WDATPConnection-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="dfff6-123">![Microsoft Defender ATP connection](../../media/Explorer-WDATPConnection-dialog.png)</span></span><br>
    
5. <span data-ttu-id="dfff6-124">Schakel de verbinding in het[https://securitycenter.windows.com](https://securitycenter.windows.com)Microsoft Defender Security Center in ( ).</span><span class="sxs-lookup"><span data-stu-id="dfff6-124">Enable the connection in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

## <a name="related-topics"></a><span data-ttu-id="dfff6-125">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="dfff6-125">Related topics</span></span>

[<span data-ttu-id="dfff6-126">Mogelijkheden voor onderzoek naar en respons op bedreigingen in Office 365</span><span class="sxs-lookup"><span data-stu-id="dfff6-126">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)
  
[<span data-ttu-id="dfff6-127">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="dfff6-127">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  

