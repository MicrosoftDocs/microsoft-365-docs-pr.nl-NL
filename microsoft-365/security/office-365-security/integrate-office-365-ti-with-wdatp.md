---
title: Microsoft Defender voor Office 365 gebruiken samen met Microsoft Defender voor eindpunt
f1.keywords:
- NOCSH
keywords: integreren, Microsoft Defender, ATP
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
description: Gebruik Microsoft Defender voor Office 365 samen met Microsoft Defender voor Eindpunt voor meer gedetailleerde informatie over bedreigingen voor uw apparaten en e-mailinhoud.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 035834e1e4855c0e47defed06043a5fdbd0e63bd
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166085"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="ff901-104">Microsoft Defender voor Office 365 gebruiken samen met Microsoft Defender voor eindpunt</span><span class="sxs-lookup"><span data-stu-id="ff901-104">Use Microsoft Defender for Office 365 together with Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="ff901-105">[Microsoft Defender voor Office 365](office-365-atp.md) kan worden geconfigureerd voor gebruik met [Microsoft Defender voor het eindpunt.](https://docs.microsoft.com/windows/security/threat-protection)</span><span class="sxs-lookup"><span data-stu-id="ff901-105">[Microsoft Defender for Office 365](office-365-atp.md) can be configured to work with [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection).</span></span>

<span data-ttu-id="ff901-106">Door Microsoft Defender voor Office 365 te integreren met Microsoft Defender voor het eindpunt, kan het team voor beveiligingsbewerkingen controleren en snel actie ondernemen als de apparaten van gebruikers risico lopen.</span><span class="sxs-lookup"><span data-stu-id="ff901-106">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint can help your security operations team monitor and take action quickly if users' devices are at risk.</span></span> <span data-ttu-id="ff901-107">Als de integratie is ingeschakeld, kan het team voor beveiligingsbewerkingen bijvoorbeeld de apparaten zien die mogelijk worden beïnvloed door een gedetecteerd e-mailbericht en kunnen er recente waarschuwingen worden gegenereerd voor deze apparaten in Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="ff901-107">For example, once integration is enabled, your security operations team will be able to see the devices that are potentially affected by a detected email message, as well as how many recent alerts were generated for those devices in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="ff901-108">In de volgende afbeelding ziet u hoe **het** tabblad Apparaten eruitziet wanneer u integratie met Microsoft Defender voor eindpunt hebt ingeschakeld:</span><span class="sxs-lookup"><span data-stu-id="ff901-108">The following image depicts what the **Devices** tab looks like when you have Microsoft Defender for Endpoint integration enabled:</span></span>

![Wanneer Microsoft Defender voor eindpunt is ingeschakeld, ziet u een lijst met apparaten met waarschuwingen.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

<span data-ttu-id="ff901-110">In dit voorbeeld ziet u dat de geadresseerden van het gedetecteerde e-mailbericht vier apparaten hebben en één apparaat een waarschuwing heeft.</span><span class="sxs-lookup"><span data-stu-id="ff901-110">In this example, you can see that the recipients of the detected email message have four devices and one has an alert.</span></span> <span data-ttu-id="ff901-111">Als u op de koppeling voor een apparaat klikt, wordt de pagina geopend in het Microsoft Defender-beveiligingscentrum <https://securitycenter.windows.com> ().</span><span class="sxs-lookup"><span data-stu-id="ff901-111">Clicking the link for a device opens its page in the Microsoft Defender Security Center (<https://securitycenter.windows.com>).</span></span>

> [!TIP]
> <span data-ttu-id="ff901-112">**[Meer informatie over het Microsoft Defender-beveiligingscentrum](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (ook wel de portal van Microsoft Defender voor eindpunt genoemd).</span><span class="sxs-lookup"><span data-stu-id="ff901-112">**[Learn more about the Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (also referred to as the Microsoft Defender for Endpoint portal.)</span></span>

## <a name="requirements"></a><span data-ttu-id="ff901-113">Vereisten</span><span class="sxs-lookup"><span data-stu-id="ff901-113">Requirements</span></span>

- <span data-ttu-id="ff901-114">Uw organisatie moet over Microsoft Defender voor Office 365 (of Office 365 E5) en Microsoft Defender voor eindpunt gaan.</span><span class="sxs-lookup"><span data-stu-id="ff901-114">Your organization must have Microsoft Defender for Office 365 (or Office 365 E5) and Microsoft Defender for Endpoint.</span></span>

- <span data-ttu-id="ff901-115">U moet een globale beheerder zijn of een rol als beveiligingsbeheerder hebben (zoals beveiligingsbeheerder) die is toegewezen in het & [compliancecentrum.](https://protection.office.com)</span><span class="sxs-lookup"><span data-stu-id="ff901-115">You must be a global administrator or have a security administrator role (such as Security Administrator) assigned in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="ff901-116">(Zie [Machtigingen in het beveiligings- & Compliancecentrum)](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="ff901-116">(See [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>

- <span data-ttu-id="ff901-117">U moet toegang hebben tot [Explorer (of realtime detecties)](threat-explorer.md) in het beveiligings- & compliancecentrum en het Microsoft Defender-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="ff901-117">You must have access to both [Explorer (or real-time detections)](threat-explorer.md) in the Security & Compliance Center and the Microsoft Defender Security Center.</span></span>

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="ff901-118">Microsoft Defender voor Office 365 integreren met Microsoft Defender voor eindpunt</span><span class="sxs-lookup"><span data-stu-id="ff901-118">To integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="ff901-119">De integratie van Microsoft Defender voor Office 365 met Microsoft Defender voor eindpunt wordt ingesteld via zowel het beveiligings- & compliancecentrum als het Microsoft Defender-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="ff901-119">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint is set up by using both the Security & Compliance Center AND the Microsoft Defender Security Center.</span></span>

1. <span data-ttu-id="ff901-120">Als globale beheerder of beveiligingsbeheerder gaat u naar en meld u <https://protection.office.com> aan.</span><span class="sxs-lookup"><span data-stu-id="ff901-120">As a global administrator or a security administrator, go to <https://protection.office.com> and sign in.</span></span> <span data-ttu-id="ff901-121">(Hiermee gaat u naar het Office 365-& compliancecentrum.)</span><span class="sxs-lookup"><span data-stu-id="ff901-121">(This takes you to the Office 365 Security & Compliance Center.)</span></span>

2. <span data-ttu-id="ff901-122">Kies **Bedreigingsbeheerverkenner** in het \> **navigatiedeelvenster.**</span><span class="sxs-lookup"><span data-stu-id="ff901-122">In the navigation pane, choose **Threat management** \> **Explorer**.</span></span>

   ![Explorer in het menu Bedreigingsbeheer](../../media/ThreatMgmt-Explorer-nav.png)

3. <span data-ttu-id="ff901-124">Kies in de rechterbovenhoek van het scherm **Defender voor eindpuntinstellingen (MDE-instellingen).**</span><span class="sxs-lookup"><span data-stu-id="ff901-124">In the upper right corner of the screen, choose **Defender for Endpoint Settings (MDE Settings)**.</span></span>

4. <span data-ttu-id="ff901-125">Schakel in het dialoogvenster Verbinding maken met Microsoft Defender voor eindpunt **verbinding in met Microsoft Defender voor eindpunt.**</span><span class="sxs-lookup"><span data-stu-id="ff901-125">In the Microsoft Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span>

   ![Verbinding met Microsoft Defender voor eindpunt](../../media/Explorer-WDATPConnection-dialog.png)

5. <span data-ttu-id="ff901-127">Ga naar het Microsoft Defender-beveiligingscentrum <https://securitycenter.windows.com> ().</span><span class="sxs-lookup"><span data-stu-id="ff901-127">Go to the Microsoft Defender Security Center (<https://securitycenter.windows.com>).</span></span>

6. <span data-ttu-id="ff901-128">Kies Instellingen op de **navigatiebalk.**</span><span class="sxs-lookup"><span data-stu-id="ff901-128">In the navigation bar, choose **Settings**.</span></span> <span data-ttu-id="ff901-129">Kies vervolgens onder **Algemeen** geavanceerde **functies.**</span><span class="sxs-lookup"><span data-stu-id="ff901-129">Then, under **General**, choose **Advanced features**.</span></span>

7. <span data-ttu-id="ff901-130">Schuif omlaag naar **De verbinding met Office 365 Threat Intelligence** en schakel de verbinding in.</span><span class="sxs-lookup"><span data-stu-id="ff901-130">Scroll down to **Office 365 Threat Intelligence connection**, and turn the connection on.</span></span>

   ![Verbinding voor bedreigingsinformatie in Office 365](../../media/mdatp-oatptoggle.png)

## <a name="related-articles"></a><span data-ttu-id="ff901-132">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="ff901-132">Related articles</span></span>

[<span data-ttu-id="ff901-133">Mogelijkheden voor bedreigingsonderzoek en -antwoorden in Office 365</span><span class="sxs-lookup"><span data-stu-id="ff901-133">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)

[<span data-ttu-id="ff901-134">Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="ff901-134">Microsoft Defender for Office 365</span></span>](office-365-atp.md)

[<span data-ttu-id="ff901-135">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="ff901-135">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection)
