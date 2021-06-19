---
title: Microsoft Defender gebruiken voor Office 365 samen met Microsoft Defender voor Eindpunt
f1.keywords:
- NOCSH
keywords: integreren, Microsoft Defender, Microsoft Defender voor Eindpunt
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 06/10/2021
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
ms.openlocfilehash: e59f608a6f732f58002dfd2ff34666865ab23f3d
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028873"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="119f4-104">Microsoft Defender gebruiken voor Office 365 samen met Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="119f4-104">Use Microsoft Defender for Office 365 together with Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="119f4-105">[Microsoft Defender voor Office 365](defender-for-office-365.md) kan worden geconfigureerd voor gebruik met [Microsoft Defender voor Eindpunt.](/windows/security/threat-protection)</span><span class="sxs-lookup"><span data-stu-id="119f4-105">[Microsoft Defender for Office 365](defender-for-office-365.md) can be configured to work with [Microsoft Defender for Endpoint](/windows/security/threat-protection).</span></span>

<span data-ttu-id="119f4-106">Als u Microsoft Defender voor Office 365 met Microsoft Defender voor Eindpunt integreert, kan uw beveiligingsteam uw beveiligingsactiviteiten helpen bij het controleren en snel actie ondernemen als de apparaten van gebruikers in gevaar zijn.</span><span class="sxs-lookup"><span data-stu-id="119f4-106">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint can help your security operations team monitor and take action quickly if users' devices are at risk.</span></span> <span data-ttu-id="119f4-107">Wanneer integratie bijvoorbeeld is ingeschakeld, kan uw beveiligingsteam de apparaten zien die mogelijk worden beïnvloed door een gedetecteerd e-mailbericht en hoeveel recente waarschuwingen er zijn gegenereerd voor die apparaten in Microsoft Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="119f4-107">For example, once integration is enabled, your security operations team will be able to see the devices that are potentially affected by a detected email message, as well as how many recent alerts were generated for those devices in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="119f4-108">In de volgende afbeelding ziet u hoe het tabblad **Apparaten** eruitziet wanneer Microsoft Defender voor endpoint-integratie is ingeschakeld:</span><span class="sxs-lookup"><span data-stu-id="119f4-108">The following image depicts what the **Devices** tab looks like when you have Microsoft Defender for Endpoint integration enabled:</span></span>

![Wanneer Microsoft Defender voor Eindpunt is ingeschakeld, ziet u een lijst met apparaten met waarschuwingen.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

<span data-ttu-id="119f4-110">In dit voorbeeld kunt u zien dat de geadresseerden van het gedetecteerde e-mailbericht vier apparaten hebben en één een waarschuwing heeft.</span><span class="sxs-lookup"><span data-stu-id="119f4-110">In this example, you can see that the recipients of the detected email message have four devices and one has an alert.</span></span> <span data-ttu-id="119f4-111">Als u op de koppeling voor een apparaat klikt, wordt de pagina geopend in [Microsoft 365 Defender](../defender-endpoint/microsoft-defender-security-center.md) (voorheen de Microsoft Defender-beveiligingscentrum).</span><span class="sxs-lookup"><span data-stu-id="119f4-111">Clicking the link for a device opens its page in [Microsoft 365 Defender](../defender-endpoint/microsoft-defender-security-center.md) (formerly the Microsoft Defender Security Center).</span></span>

> [!TIP]
> <span data-ttu-id="119f4-112">De Microsoft 365 Defender portal vervangt de Microsoft Defender-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="119f4-112">The Microsoft 365 Defender portal replaces the Microsoft Defender Security Center.</span></span> <span data-ttu-id="119f4-113">Zie [Microsoft Defender voor Eindpunt in Microsoft 365 Defender.](../defender/microsoft-365-security-center-mde.md)</span><span class="sxs-lookup"><span data-stu-id="119f4-113">See [Microsoft Defender for Endpoint in Microsoft 365 Defender](../defender/microsoft-365-security-center-mde.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="119f4-114">Vereisten</span><span class="sxs-lookup"><span data-stu-id="119f4-114">Requirements</span></span>

- <span data-ttu-id="119f4-115">Uw organisatie moet Microsoft Defender hebben voor Office 365 (of Office 365 E5) en Microsoft Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="119f4-115">Your organization must have Microsoft Defender for Office 365 (or Office 365 E5) and Microsoft Defender for Endpoint.</span></span>

- <span data-ttu-id="119f4-116">U moet een globale beheerder zijn of een beveiligingsbeheerderrol (zoals beveiligingsbeheerder) hebben toegewezen in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="119f4-116">You must be a global administrator or have a security administrator role (such as Security Administrator) assigned in Microsoft 365.</span></span> <span data-ttu-id="119f4-117">(Zie [Machtigingen in de Microsoft 365 Defender](permissions-in-the-security-and-compliance-center.md))</span><span class="sxs-lookup"><span data-stu-id="119f4-117">(See [Permissions in the Microsoft 365 Defender](permissions-in-the-security-and-compliance-center.md))</span></span>

- <span data-ttu-id="119f4-118">U moet toegang hebben tot [Explorer (of realtimedetecties).](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="119f4-118">You must have access to [Explorer (or real-time detections)](threat-explorer.md).</span></span>

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="119f4-119">Microsoft Defender voor Office 365 integreren met Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="119f4-119">To integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="119f4-120">De integratie van Microsoft Defender voor Office 365 met Microsoft Defender voor Eindpunt is ingesteld in zowel Defender voor Eindpunt als Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="119f4-120">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint is set up in both Defender for Endpoint and Defender for Office 365.</span></span>

1. <span data-ttu-id="119f4-121">Als globale beheerder of beveiligingsbeheerder gaat u naar [https://security.microsoft.com](https://security.microsoft.com) en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="119f4-121">As a global administrator or a security administrator, go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> <span data-ttu-id="119f4-122">(Hiermee gaat u naar de Microsoft 365 Defender portal.)</span><span class="sxs-lookup"><span data-stu-id="119f4-122">(This takes you to the Microsoft 365 Defender portal.)</span></span>

2. <span data-ttu-id="119f4-123">Kies in het navigatiedeelvenster **E-mail & Samenwerkingsverkenner** \> .</span><span class="sxs-lookup"><span data-stu-id="119f4-123">In the navigation pane, choose **Email & collaboration** \> **Explorer**.</span></span>

3. <span data-ttu-id="119f4-124">Klik in de rechterbovenhoek van het scherm op **MDE-Instellingen.**</span><span class="sxs-lookup"><span data-stu-id="119f4-124">In the upper right corner of the screen, click **MDE Settings**.</span></span>

4. <span data-ttu-id="119f4-125">Schakel in het dialoogvenster Verbinding met Microsoft Defender voor eindpunt de Verbinding maken **microsoft Defender voor eindpunt in.**</span><span class="sxs-lookup"><span data-stu-id="119f4-125">In the Microsoft Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span>

    :::image type="content" source="../../media/explorer-mdeconnection-dialognew.png" alt-text="MDE-verbinding":::

5. <span data-ttu-id="119f4-127">Ga naar de Microsoft 365 Defender portal ( [https://security.microsoft.com](https://security.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="119f4-127">Go to the Microsoft 365 Defender portal ([https://security.microsoft.com](https://security.microsoft.com).</span></span>

6. <span data-ttu-id="119f4-128">Kies in de navigatiebalk **Instellingen.**</span><span class="sxs-lookup"><span data-stu-id="119f4-128">In the navigation bar, choose **Settings**.</span></span> <span data-ttu-id="119f4-129">Kies vervolgens onder **Algemeen** de optie **Geavanceerde functies.**</span><span class="sxs-lookup"><span data-stu-id="119f4-129">Then, under **General**, choose **Advanced features**.</span></span>

7. <span data-ttu-id="119f4-130">Schuif omlaag naar **Office 365 Threat Intelligence-verbinding** en schakel de verbinding in.</span><span class="sxs-lookup"><span data-stu-id="119f4-130">Scroll down to **Office 365 Threat Intelligence connection**, and turn the connection on.</span></span>

   ![Office 365 threat intelligence-verbinding](../../media/mdatp-oatptoggle.png)

## <a name="related-articles"></a><span data-ttu-id="119f4-132">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="119f4-132">Related articles</span></span>

[<span data-ttu-id="119f4-133">Mogelijkheden voor het onderzoeken en reageren van bedreigingen in Office 365</span><span class="sxs-lookup"><span data-stu-id="119f4-133">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)

[<span data-ttu-id="119f4-134">Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="119f4-134">Microsoft Defender for Office 365</span></span>](defender-for-office-365.md)

[<span data-ttu-id="119f4-135">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="119f4-135">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection)
