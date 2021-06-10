---
title: Microsoft Defender gebruiken voor Office 365 samen met Microsoft Defender voor Eindpunt
f1.keywords:
- NOCSH
keywords: integreren, Microsoft Defender, Microsoft Defender voor Eindpunt
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 01/21/2021
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Gebruik Microsoft Defender voor Office 365 samen met Microsoft Defender voor Eindpunt voor meer gedetailleerde informatie over bedreigingen tegen uw apparaten en e-mailinhoud.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e6ad81102a9702a725f40fcdb5421a2b19b0086d
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934031"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="d0bcf-104">Microsoft Defender gebruiken voor Office 365 samen met Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="d0bcf-104">Use Microsoft Defender for Office 365 together with Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="d0bcf-105">[Microsoft Defender voor Office 365](defender-for-office-365.md) kan worden geconfigureerd voor gebruik met [Microsoft Defender voor Eindpunt.](/windows/security/threat-protection)</span><span class="sxs-lookup"><span data-stu-id="d0bcf-105">[Microsoft Defender for Office 365](defender-for-office-365.md) can be configured to work with [Microsoft Defender for Endpoint](/windows/security/threat-protection).</span></span>

<span data-ttu-id="d0bcf-106">Als u Microsoft Defender voor Office 365 met Microsoft Defender voor Eindpunt integreert, kan uw beveiligingsteam uw beveiligingsactiviteiten helpen bij het controleren en snel actie ondernemen als de apparaten van gebruikers in gevaar zijn.</span><span class="sxs-lookup"><span data-stu-id="d0bcf-106">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint can help your security operations team monitor and take action quickly if users' devices are at risk.</span></span> <span data-ttu-id="d0bcf-107">Wanneer integratie bijvoorbeeld is ingeschakeld, kan uw beveiligingsteam de apparaten zien die mogelijk worden beïnvloed door een gedetecteerd e-mailbericht en hoeveel recente waarschuwingen er zijn gegenereerd voor die apparaten in Microsoft Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="d0bcf-107">For example, once integration is enabled, your security operations team will be able to see the devices that are potentially affected by a detected email message, as well as how many recent alerts were generated for those devices in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="d0bcf-108">In de volgende afbeelding ziet u hoe het tabblad **Apparaten** eruitziet wanneer Microsoft Defender voor endpoint-integratie is ingeschakeld:</span><span class="sxs-lookup"><span data-stu-id="d0bcf-108">The following image depicts what the **Devices** tab looks like when you have Microsoft Defender for Endpoint integration enabled:</span></span>

![Wanneer Microsoft Defender voor Eindpunt is ingeschakeld, ziet u een lijst met apparaten met waarschuwingen.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

<span data-ttu-id="d0bcf-110">In dit voorbeeld kunt u zien dat de geadresseerden van het gedetecteerde e-mailbericht vier apparaten hebben en één een waarschuwing heeft.</span><span class="sxs-lookup"><span data-stu-id="d0bcf-110">In this example, you can see that the recipients of the detected email message have four devices and one has an alert.</span></span> <span data-ttu-id="d0bcf-111">Als u op de koppeling voor een apparaat klikt, wordt de pagina geopend in de Microsoft Defender-beveiligingscentrum ( <https://securitycenter.windows.com> ).</span><span class="sxs-lookup"><span data-stu-id="d0bcf-111">Clicking the link for a device opens its page in the Microsoft Defender Security Center (<https://securitycenter.windows.com>).</span></span>

> [!TIP]
> <span data-ttu-id="d0bcf-112">**[Meer informatie over de Microsoft Defender-beveiligingscentrum](/windows/security/threat-protection/microsoft-defender-atp/use)** (ook wel de Microsoft Defender for Endpoint-portal genoemd.)</span><span class="sxs-lookup"><span data-stu-id="d0bcf-112">**[Learn more about the Microsoft Defender Security Center](/windows/security/threat-protection/microsoft-defender-atp/use)** (also referred to as the Microsoft Defender for Endpoint portal.)</span></span>

## <a name="requirements"></a><span data-ttu-id="d0bcf-113">Vereisten</span><span class="sxs-lookup"><span data-stu-id="d0bcf-113">Requirements</span></span>

- <span data-ttu-id="d0bcf-114">Uw organisatie moet Microsoft Defender hebben voor Office 365 (of Office 365 E5) en Microsoft Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="d0bcf-114">Your organization must have Microsoft Defender for Office 365 (or Office 365 E5) and Microsoft Defender for Endpoint.</span></span>

- <span data-ttu-id="d0bcf-115">U moet een globale beheerder zijn of een beveiligingsbeheerderrol (zoals beveiligingsbeheerder) hebben toegewezen in het Beveiligings- [& Compliancecentrum.](https://protection.office.com)</span><span class="sxs-lookup"><span data-stu-id="d0bcf-115">You must be a global administrator or have a security administrator role (such as Security Administrator) assigned in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="d0bcf-116">(Zie [Machtigingen in het beveiligings- & Compliancecentrum](permissions-in-the-security-and-compliance-center.md))</span><span class="sxs-lookup"><span data-stu-id="d0bcf-116">(See [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>

- <span data-ttu-id="d0bcf-117">U moet toegang hebben tot [Zowel Explorer (of realtime detecties)](threat-explorer.md) in het Beveiligings- & compliancecentrum als de Microsoft Defender-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="d0bcf-117">You must have access to both [Explorer (or real-time detections)](threat-explorer.md) in the Security & Compliance Center and the Microsoft Defender Security Center.</span></span>

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="d0bcf-118">Microsoft Defender voor Office 365 integreren met Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="d0bcf-118">To integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="d0bcf-119">De integratie van Microsoft Defender voor Office 365 met Microsoft Defender voor Eindpunt wordt ingesteld met behulp van zowel het Beveiligings- & Compliancecentrum als de Microsoft Defender-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="d0bcf-119">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint is set up by using both the Security & Compliance Center AND the Microsoft Defender Security Center.</span></span>

1. <span data-ttu-id="d0bcf-120">Als globale beheerder of beveiligingsbeheerder gaat u naar <https://protection.office.com> en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="d0bcf-120">As a global administrator or a security administrator, go to <https://protection.office.com> and sign in.</span></span> <span data-ttu-id="d0bcf-121">(Hiermee gaat u naar het Office 365 beveiligings- & compliancecentrum.)</span><span class="sxs-lookup"><span data-stu-id="d0bcf-121">(This takes you to the Office 365 Security & Compliance Center.)</span></span>

2. <span data-ttu-id="d0bcf-122">Kies in het navigatiedeelvenster **Bedreigingsbeheer** \> **Explorer.**</span><span class="sxs-lookup"><span data-stu-id="d0bcf-122">In the navigation pane, choose **Threat management** \> **Explorer**.</span></span>

   ![Explorer in het menu Bedreigingsbeheer](../../media/ThreatMgmt-Explorer-nav.png)

3. <span data-ttu-id="d0bcf-124">Kies in de rechterbovenhoek van het scherm **De optie Defender voor eindpunten Instellingen (MDE Instellingen)**.</span><span class="sxs-lookup"><span data-stu-id="d0bcf-124">In the upper right corner of the screen, choose **Defender for Endpoint Settings (MDE Settings)**.</span></span>

4. <span data-ttu-id="d0bcf-125">Schakel in het dialoogvenster Verbinding met Microsoft Defender voor eindpunt de Verbinding maken **microsoft Defender voor eindpunt in.**</span><span class="sxs-lookup"><span data-stu-id="d0bcf-125">In the Microsoft Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span>

   ![Verbinding met Microsoft Defender voor eindpunt](../../media/Explorer-WDATPConnection-dialog.png)

5. <span data-ttu-id="d0bcf-127">Ga naar de Microsoft Defender-beveiligingscentrum ( <https://securitycenter.windows.com> ).</span><span class="sxs-lookup"><span data-stu-id="d0bcf-127">Go to the Microsoft Defender Security Center (<https://securitycenter.windows.com>).</span></span>

6. <span data-ttu-id="d0bcf-128">Kies in de navigatiebalk **Instellingen.**</span><span class="sxs-lookup"><span data-stu-id="d0bcf-128">In the navigation bar, choose **Settings**.</span></span> <span data-ttu-id="d0bcf-129">Kies vervolgens onder **Algemeen** de optie **Geavanceerde functies.**</span><span class="sxs-lookup"><span data-stu-id="d0bcf-129">Then, under **General**, choose **Advanced features**.</span></span>

7. <span data-ttu-id="d0bcf-130">Schuif omlaag naar **Office 365 Threat Intelligence-verbinding** en schakel de verbinding in.</span><span class="sxs-lookup"><span data-stu-id="d0bcf-130">Scroll down to **Office 365 Threat Intelligence connection**, and turn the connection on.</span></span>

   ![Office 365 threat intelligence-verbinding](../../media/mdatp-oatptoggle.png)

## <a name="related-articles"></a><span data-ttu-id="d0bcf-132">Aanverwante artikelen</span><span class="sxs-lookup"><span data-stu-id="d0bcf-132">Related articles</span></span>

[<span data-ttu-id="d0bcf-133">Mogelijkheden voor het onderzoeken en reageren van bedreigingen in Office 365</span><span class="sxs-lookup"><span data-stu-id="d0bcf-133">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)

[<span data-ttu-id="d0bcf-134">Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="d0bcf-134">Microsoft Defender for Office 365</span></span>](defender-for-office-365.md)

[<span data-ttu-id="d0bcf-135">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="d0bcf-135">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection)